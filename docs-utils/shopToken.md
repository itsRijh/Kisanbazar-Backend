## `sendShopToken` Function

The `sendShopToken` function is responsible for creating a token and saving it in cookies. It takes three parameters: `user`, `statusCode`, and `res`.

### Parameters

- `user`: The user object.
- `statusCode`: The HTTP status code to be sent in the response.
- `res`: The response object.

### Usage

```javascript
const sendShopToken = require('./sendShopToken');

// Example usage
sendShopToken(user, 200, res);
```

### Example Response

The function will set a cookie named "seller_token" with the generated token and send a JSON response with the following structure:

```json
{
    "success": true,
    "user": { /* user object */ },
    "token": "generated_token"
}
```

### Cookie Options

The function sets the following options for the cookie:

- `expires`: The expiration date of the cookie (90 days from the current date).
- `httpOnly`: The cookie is only accessible via HTTP(S) and not JavaScript.
- `sameSite`: The cookie is not restricted to same-site requests.
- `secure`: The cookie can only be sent over HTTPS.

## jwtToken.md

This file contains the code for generating a JWT token and saving it in cookies.

```javascript
const sendToken = (user, statusCode, res) => {
    const token = user.getJwtToken();

    // Options for cookies
    const options = {
        expires: new Date(Date.now() + 90 * 24 * 60 * 60 * 1000),
        httpOnly: true,
        sameSite: "none",
        secure: true,
    };

    res.status(statusCode).cookie("token", token, options).json({
        success: true,
        user,
        token,
    });
};

module.exports = sendToken;
```

The `sendToken` function takes in three parameters: `user`, `statusCode`, and `res`. It generates a JWT token using the `getJwtToken` method of the `user` object. The token is then saved in a cookie named "token" with the specified options.

The `options` object defines the expiration date of the cookie (`90` days from the current date), sets the `httpOnly` flag to `true` to prevent client-side access to the cookie, and ensures that the cookie is only sent over secure connections (`sameSite: "none"` and `secure: true`).

Finally, the function sends a JSON response with the `success` flag set to `true`, the `user` object, and the generated `token`.

This code can be used to handle token generation and cookie management in a backend application.

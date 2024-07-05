# Error Middleware Documentation

This documentation provides an overview of the error middleware code snippet provided.

## Usage

The error middleware is used to handle and format errors in an Express.js application. It takes four parameters: `err`, `req`, `res`, and `next`.

```javascript
const ErrorHandler = require("../utils/ErrorHandler");

module.exports = (err, req, res, next) => {
    // Set default status code and message
    err.statusCode = err.statusCode || 500;
    err.message = err.message || "Internal server Error";

    // Handle CastError (wrong MongoDB ID)
    if (err.name === "CastError") {
        const message = `Resources not found with this ID. Invalid ${err.path}`;
        err = new ErrorHandler(message, 400);
    }

    // Handle Duplicate key error
    if (err.code === 11000) {
        const message = `Duplicate key ${Object.keys(err.keyValue)} entered`;
        err = new ErrorHandler(message, 400);
    }

    // Handle wrong JWT error
    if (err.name === "JsonWebTokenError") {
        const message = `Your URL is invalid. Please try again later`;
        err = new ErrorHandler(message, 400);
    }

    // Handle JWT expired error
    if (err.name === "TokenExpiredError") {
        const message = `Your URL has expired. Please try again later!`;
        err = new ErrorHandler(message, 400);
    }

    // Send error response
    res.status(err.statusCode).json({
        success: false,
        message: err.message,
    });
};
```

## Error Handling

The error middleware handles various types of errors:

- `CastError`: This error occurs when an invalid MongoDB ID is provided. The middleware sets the status code to 400 (Bad Request) and returns an error message indicating the invalid ID.

- `Duplicate key error`: This error occurs when a duplicate key is entered. The middleware sets the status code to 400 (Bad Request) and returns an error message indicating the duplicate key.

- `JsonWebTokenError`: This error occurs when the provided JWT is invalid. The middleware sets the status code to 400 (Bad Request) and returns an error message indicating the invalid URL.

- `TokenExpiredError`: This error occurs when the provided JWT has expired. The middleware sets the status code to 400 (Bad Request) and returns an error message indicating the expired URL.

## Response

The middleware sends a JSON response with the following structure:

```json
{
    "success": false,
    "message": "Error message"
}
```

The `success` field indicates whether the request was successful or not, and the `message` field contains the error message.

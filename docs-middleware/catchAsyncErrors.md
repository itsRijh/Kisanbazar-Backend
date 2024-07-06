## catchAsyncErrors Middleware

This middleware function wraps another function and handles any asynchronous errors that may occur during its execution.

### Usage

```javascript
const catchAsyncErrors = require('./catchAsyncErrors');

// Define your route handler function
const myRouteHandler = (req, res, next) => {
    // Your code here
};

// Wrap the route handler function with catchAsyncErrors middleware
const wrappedRouteHandler = catchAsyncErrors(myRouteHandler);

// Use the wrapped route handler in your route definition
app.get('/my-route', wrappedRouteHandler);
```

### Description

The `catchAsyncErrors` middleware is a higher-order function that takes in a function (`theFunc`) as an argument and returns a new function that can be used as middleware in an Express route. This middleware function ensures that any asynchronous errors thrown by `theFunc` are caught and passed to the Express error handling middleware (`next`).

### Parameters

- `theFunc` (Function): The function to be wrapped with error handling. It should have the signature `(req, res, next)`.

### Example

```javascript
const catchAsyncErrors = require('./catchAsyncErrors');

const myAsyncFunction = async (req, res, next) => {
    // Asynchronous code that may throw an error
};

const wrappedAsyncFunction = catchAsyncErrors(myAsyncFunction);

app.get('/my-route', wrappedAsyncFunction);
```

In the above example, `myAsyncFunction` is wrapped with `catchAsyncErrors` middleware and then used as the route handler for the `/my-route` route. Any errors thrown by `myAsyncFunction` will be caught and passed to the Express error handling middleware.

# ErrorHandler Documentation

The `ErrorHandler` class is a custom error class that extends the built-in `Error` class. It is used to handle and manage errors in the application.

## Constructor

### Parameters

- `message` (string): The error message.
- `statusCode` (number): The HTTP status code associated with the error.

### Example

```javascript
const errorHandler = new ErrorHandler('An error occurred', 500);
```

## Properties

- `statusCode` (number): The HTTP status code associated with the error.

## Methods

The `ErrorHandler` class does not have any additional methods.

## Usage

To use the `ErrorHandler` class, you can import it into your application and create an instance of it with the appropriate error message and status code.

```javascript
const ErrorHandler = require('./ErrorHandler');

try {
    // Some code that may throw an error
} catch (error) {
    const errorHandler = new ErrorHandler('An error occurred', 500);
    // Handle the error using the `errorHandler` instance
}
```

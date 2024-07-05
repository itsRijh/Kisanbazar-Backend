## Authentication Middleware Documentation

This documentation provides an overview of the authentication middleware functions used in the Kisanbazar-Backend project.

### isAuthenticated

This middleware function is used to check if a user is authenticated. It verifies the presence of a token in the request cookies and decodes it using the JWT secret key. If the token is valid, it sets the `req.user` property to the corresponding user object retrieved from the database.

#### Usage

```javascript
const { isAuthenticated } = require('./middleware/auth');

app.get('/protected-route', isAuthenticated, (req, res) => {
    // Access protected route logic here
});
```

### isSeller

This middleware function is used to check if a user is a seller. It verifies the presence of a seller token in the request cookies and decodes it using the JWT secret key. If the token is valid, it sets the `req.seller` property to the corresponding shop object retrieved from the database.

#### Usage

```javascript
const { isSeller } = require('./middleware/auth');

app.get('/seller-route', isSeller, (req, res) => {
    // Access seller route logic here
});
```

### isAdmin

This middleware function is used to check if a user has admin privileges. It takes an array of roles as arguments and returns a middleware function. The returned middleware function checks if the `req.user.role` is included in the provided roles array. If not, it throws an error.

#### Usage

```javascript
const { isAdmin } = require('./middleware/auth');

app.get('/admin-route', isAdmin('admin'), (req, res) => {
    // Access admin route logic here
});
```

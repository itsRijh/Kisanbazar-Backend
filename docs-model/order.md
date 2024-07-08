
# Order Model

This is the documentation for the `Order` model in the Kisanbazar-Backend project.

## Schema

The `Order` schema has the following fields:

- `cart` (Array, required): Represents the items in the cart.
- `shippingAddress` (Object, required): Represents the shipping address.
- `user` (Object, required): Represents the user who placed the order.
- `totalPrice` (Number, required): Represents the total price of the order.
- `status` (String, default: "Processing"): Represents the status of the order.
- `paymentInfo` (Object): Represents the payment information.
    - `id` (String): Represents the payment ID.
    - `status` (String): Represents the payment status.
    - `type` (String): Represents the payment type.
- `paidAt` (Date, default: current date and time): Represents the date and time when the order was paid.
- `deliveredAt` (Date): Represents the date and time when the order was delivered.
- `createdAt` (Date, default: current date and time): Represents the date and time when the order was created.

## Usage

To use the `Order` model, you can import it as follows:

```javascript
const Order = require("path/to/order/model");

// Example usage
const order = new Order({
    cart: [...],
    shippingAddress: {...},
    user: {...},
    totalPrice: ...,
    status: ...,
    paymentInfo: {...},
    paidAt: ...,
    deliveredAt: ...,
    createdAt: ...,
});
```

Please note that this is just a sample documentation and you may need to adjust it based on your specific implementation.
```
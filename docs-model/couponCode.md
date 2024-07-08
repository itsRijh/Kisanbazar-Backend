
# Coupon Code

This document describes the structure and properties of the `CoupounCode` model in the Kisanbazar Backend application.

## Schema

The `CoupounCode` model has the following properties:

- `name` (String, required): The name of the coupon code. Must be unique.
- `value` (Number, required): The value of the coupon code.
- `minAmount` (Number): The minimum amount required for the coupon code to be applicable.
- `maxAmount` (Number): The maximum amount for which the coupon code can be applied.
- `shopId` (String, required): The ID of the shop associated with the coupon code.
- `selectedProduct` (String): The selected product for which the coupon code is applicable.
- `createdAt` (Date): The date and time when the coupon code was created. Defaults to the current date and time.

## Usage

To use the `CoupounCode` model in your application, import it as follows:

```javascript
const CoupounCode = require("path/to/couponCodeModel");

// Use the model to create, update, or query coupon codes
```
```
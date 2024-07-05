## payment.md

This file contains the code for handling payments using Stripe in the Kisanbazar-Backend project.

### Dependencies

- express
- stripe

### Usage

```javascript
const express = require("express");
const router = express.Router();
const catchAsyncErrors = require("../middleware/catchAsyncErrors");

const stripe = require("stripe")(process.env.STRIPE_SECRET_KEY);

router.post(
    "/process",
    catchAsyncErrors(async (req, res, next) => {
        const myPayment = await stripe.paymentIntents.create({
            amount: req.body.amount,
            currency: "inr",
            metadata: {
                company: "Becodemy",
            },
        });
        res.status(200).json({
            success: true,
            client_secret: myPayment.client_secret,
        });
    })
);

router.get(
    "/stripeapikey",
    catchAsyncErrors(async (req, res, next) => {
        res.status(200).json({ stripeApikey: process.env.STRIPE_API_KEY });
    })
);

module.exports = router;
```

This module exports an Express router that handles payment-related routes. It uses the `stripe` package to interact with the Stripe API.

#### POST /process

This route is used to process a payment. It expects a JSON payload with the `amount` field specifying the payment amount in INR (Indian Rupees). The route creates a payment intent using the Stripe API and returns the client secret for the payment intent.

#### GET /stripeapikey

This route is used to retrieve the Stripe API key. It returns the API key stored in the `STRIPE_API_KEY` environment variable.

Make sure to set the `STRIPE_SECRET_KEY` and `STRIPE_API_KEY` environment variables before using this module.

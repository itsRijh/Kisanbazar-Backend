
# Event Model

This is the documentation for the Event model in the Kisanbazar-Backend project.

## Schema

The Event model has the following schema:

- `name` (String, required): The name of the event product.
- `description` (String, required): The description of the event product.
- `category` (String, required): The category of the event product.
- `start_Date` (Date, required): The start date of the event.
- `Finish_Date` (Date, required): The finish date of the event.
- `status` (String, default: "Running"): The status of the event.
- `tags` (String): The tags associated with the event.
- `originalPrice` (Number): The original price of the event product.
- `discountPrice` (Number, required): The discounted price of the event product.
- `stock` (Number, required): The stock quantity of the event product.
- `images` (Array): An array of objects representing the images of the event product. Each object has the following properties:
    - `public_id` (String, required): The public ID of the image.
    - `url` (String, required): The URL of the image.
- `shopId` (String, required): The ID of the shop associated with the event product.
- `shop` (Object, required): The details of the shop associated with the event product.
- `sold_out` (Number, default: 0): The quantity of the event product that has been sold.
- `createdAt` (Date, default: current date): The date and time when the event product was created.

## Usage

To use the Event model, you need to import it and create a new instance of it using the `mongoose.model` method. Here's an example:

```javascript
const mongoose = require("mongoose");
const eventSchema = require("./eventSchema");

const Event = mongoose.model("Event", eventSchema);

// Now you can use the Event model to perform database operations
```

Remember to replace `./eventSchema` with the correct path to the event schema file.

```
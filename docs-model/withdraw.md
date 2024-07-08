# Withdraw Model

This is the schema definition for the Withdraw model in the Kisanbazar-Backend project.

## Schema

- `seller` (Object, required): The seller object associated with the withdrawal.
- `amount` (Number, required): The amount of the withdrawal.
- `status` (String, default: "Processing"): The status of the withdrawal.
- `createdAt` (Date, default: current date and time): The date and time when the withdrawal was created.
- `updatedAt` (Date): The date and time when the withdrawal was last updated.

## Usage

To use this model in your code, you can import it as follows:

```javascript
const Withdraw = require("./path/to/withdrawModel");
```

Make sure to replace `"./path/to/withdrawModel"` with the actual path to the `withdrawModel.js` file in your project.

```
Withdraw.find({}).then((withdrawals) => {
    // Do something with the withdrawals
}).catch((error) => {
    // Handle the error
});
```

Remember to handle any errors that may occur during the database operations.

```
Withdraw.create({
    seller: { /* seller object */ },
    amount: 100,
}).then((withdrawal) => {
    // Do something with the created withdrawal
}).catch((error) => {
    // Handle the error
});
```

This is an example of how to create a new withdrawal entry in the database.

```
Withdraw.updateOne({ _id: withdrawalId }, { status: "Completed" }).then(() => {
    // Update successful
}).catch((error) => {
    // Handle the error
});
```

This is an example of how to update the status of a withdrawal entry in the database.

```
Withdraw.deleteOne({ _id: withdrawalId }).then(() => {
    // Deletion successful
}).catch((error) => {
    // Handle the error
});
```

This is an example of how to delete a withdrawal entry from the database.
```

Remember to replace `withdrawalId` with the actual ID of the withdrawal entry you want to update or delete.

That's it! You now have a basic understanding of the Withdraw model and how to use it in your Kisanbazar-Backend project.
```
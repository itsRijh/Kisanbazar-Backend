# sendMail Documentation

This module exports a function named `sendMail` that is used to send emails using Nodemailer.

## Installation

To use this module, you need to have Nodemailer installed in your project. You can install it by running the following command:

```bash
npm install nodemailer
```

## Usage

To send an email, you can call the `sendMail` function and pass an `options` object with the following properties:

- `email` (string): The recipient's email address.
- `subject` (string): The subject of the email.
- `message` (string): The content of the email.

Here's an example of how to use the `sendMail` function:

```javascript
const sendMail = require("./sendMail");

const options = {
    email: "recipient@example.com",
    subject: "Hello",
    message: "This is the body of the email.",
};

sendMail(options)
    .then(() => {
        console.log("Email sent successfully.");
    })
    .catch((error) => {
        console.error("Failed to send email:", error);
    });
```

Make sure to set the following environment variables before using the `sendMail` function:

- `SMPT_HOST`: The SMTP server host.
- `SMPT_PORT`: The SMTP server port.
- `SMPT_SERVICE`: The SMTP service name.
- `SMPT_MAIL`: The sender's email address.
- `SMPT_PASSWORD`: The sender's email password.

## License

This module is released under the MIT License. See the [LICENSE](./LICENSE) file for more information.

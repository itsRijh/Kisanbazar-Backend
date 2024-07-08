# Messages Model

This is the documentation for the Messages model in the Kisanbazar-Backend project.

## Schema

The Messages model has the following schema:

- `conversationId` (String): The ID of the conversation associated with the message.
- `text` (String): The text content of the message.
- `sender` (String): The sender of the message.
- `images` (Object): An object containing information about any images attached to the message.
    - `public_id` (String): The public ID of the image.
    - `url` (String): The URL of the image.

## Timestamps

The Messages model includes timestamps for the following fields:

- `createdAt`: The date and time when the message was created.
- `updatedAt`: The date and time when the message was last updated.
```
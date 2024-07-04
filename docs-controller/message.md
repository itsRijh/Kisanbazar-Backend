## Message API Documentation

This documentation provides information about the API endpoints for managing messages in the Kisanbazar-Backend application.

### Create New Message

Endpoint: `/create-new-message`

Method: `POST`

Description: Creates a new message.

Request Body:
```json
{
    "conversationId": "string",
    "sender": "string",
    "text": "string",
    "images": "string"
}
```

Response:
```json
{
    "success": true,
    "message": {
        "conversationId": "string",
        "text": "string",
        "sender": "string",
        "images": {
            "public_id": "string",
            "url": "string"
        }
    }
}
```

### Get All Messages

Endpoint: `/get-all-messages/:id`

Method: `GET`

Description: Retrieves all messages with the specified conversation ID.

Parameters:
- `id` (string): The conversation ID.

Response:
```json
{
    "success": true,
    "messages": [
        {
            "conversationId": "string",
            "text": "string",
            "sender": "string",
            "images": {
                "public_id": "string",
                "url": "string"
            }
        }
    ]
}
```

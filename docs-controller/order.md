# Order API Documentation

This documentation provides information about the Order API endpoints.

## Create New Message

Create a new message in a conversation.

### Request

- Method: POST
- Endpoint: `/create-new-message`

#### Request Body

| Parameter        | Type   | Description                          |
| ---------------- | ------ | ------------------------------------ |
| conversationId   | String | ID of the conversation                |
| sender           | String | Sender of the message                 |
| text             | String | Text content of the message           |
| images (optional)| String | Images attached to the message        |

### Response

- Status Code: 201 - Created

#### Response Body

```json
{
    "success": true,
    "message": {
        "_id": "message_id",
        "conversationId": "conversation_id",
        "text": "message_text",
        "sender": "message_sender",
        "images": {
            "public_id": "image_public_id",
            "url": "image_url"
        }
    }
}
```

## Get All Messages

Get all messages in a conversation.

### Request

- Method: GET
- Endpoint: `/get-all-messages/:id`

#### Request Parameters

| Parameter | Type   | Description              |
| --------- | ------ | ------------------------ |
| id        | String | ID of the conversation   |

### Response

- Status Code: 200 - OK

#### Response Body

```json
{
    "success": true,
    "messages": [
        {
            "_id": "message_id",
            "conversationId": "conversation_id",
            "text": "message_text",
            "sender": "message_sender",
            "images": {
                "public_id": "image_public_id",
                "url": "image_url"
            }
        },
        ...
    ]
}
```

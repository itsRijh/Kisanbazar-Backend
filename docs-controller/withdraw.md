# Withdraw API Documentation

This documentation provides information about the Withdraw API endpoints.

## Create Withdraw Request

Endpoint: `/create-withdraw-request`

Method: `POST`

Access: Only for sellers

Request Body:
```json
{
    "amount": 1000
}
```

Response:
```json
{
    "success": true
}
```

## Get All Withdraw Requests

Endpoint: `/get-all-withdraw-request`

Method: `GET`

Access: Admin only

Response:
```json
{
    "success": true,
    "withdraws": [
        {
            "_id": "withdraw_id",
            "seller": "seller_id",
            "amount": 1000,
            "status": "succeed",
            "createdAt": "2022-01-01T00:00:00.000Z",
            "updatedAt": "2022-01-01T00:00:00.000Z"
        },
        ...
    ]
}
```

## Update Withdraw Request

Endpoint: `/update-withdraw-request/:id`

Method: `PUT`

Access: Admin only

Request Body:
```json
{
    "sellerId": "seller_id"
}
```

Response:
```json
{
    "success": true,
    "withdraw": {
        "_id": "withdraw_id",
        "seller": "seller_id",
        "amount": 1000,
        "status": "succeed",
        "createdAt": "2022-01-01T00:00:00.000Z",
        "updatedAt": "2022-01-01T00:00:00.000Z"
    }
}
```

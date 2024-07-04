# Coupoun Code API Documentation

This documentation provides details about the API endpoints for managing coupoun codes in the Kisanbazar Backend.

## Create Coupoun Code

Create a new coupoun code.

### Request

- Method: POST
- URL: `/create-coupon-code`
- Headers:
    - Content-Type: application/json
    - Authorization: Bearer \<access_token\>

#### Request Body

```json
{
    "name": "COUPON_CODE_NAME",
    "value": "COUPON_CODE_VALUE",
    "expiryDate": "COUPON_CODE_EXPIRY_DATE"
}
```

### Response

- Status: 201 Created
- Body:

```json
{
    "success": true,
    "coupounCode": {
        "_id": "COUPON_CODE_ID",
        "name": "COUPON_CODE_NAME",
        "value": "COUPON_CODE_VALUE",
        "expiryDate": "COUPON_CODE_EXPIRY_DATE",
        "createdAt": "COUPON_CODE_CREATED_AT",
        "updatedAt": "COUPON_CODE_UPDATED_AT"
    }
}
```

## Get All Coupons of a Shop

Get all coupoun codes associated with a shop.

### Request

- Method: GET
- URL: `/get-coupon/:id`
- Headers:
    - Content-Type: application/json
    - Authorization: Bearer \<access_token\>

### Response

- Status: 200 OK
- Body:

```json
{
    "success": true,
    "couponCodes": [
        {
            "_id": "COUPON_CODE_ID",
            "name": "COUPON_CODE_NAME",
            "value": "COUPON_CODE_VALUE",
            "expiryDate": "COUPON_CODE_EXPIRY_DATE",
            "createdAt": "COUPON_CODE_CREATED_AT",
            "updatedAt": "COUPON_CODE_UPDATED_AT"
        },
        ...
    ]
}
```

## Delete Coupoun Code of a Shop

Delete a coupoun code associated with a shop.

### Request

- Method: DELETE
- URL: `/delete-coupon/:id`
- Headers:
    - Content-Type: application/json
    - Authorization: Bearer \<access_token\>

### Response

- Status: 200 OK
- Body:

```json
{
    "success": true,
    "message": "Coupon code deleted successfully!"
}
```

## Get Coupon Code Value by Name

Get the value of a coupoun code by its name.

### Request

- Method: GET
- URL: `/get-coupon-value/:name`
- Headers:
    - Content-Type: application/json

### Response

- Status: 200 OK
- Body:

```json
{
    "success": true,
    "couponCode": {
        "_id": "COUPON_CODE_ID",
        "name": "COUPON_CODE_NAME",
        "value": "COUPON_CODE_VALUE",
        "expiryDate": "COUPON_CODE_EXPIRY_DATE",
        "createdAt": "COUPON_CODE_CREATED_AT",
        "updatedAt": "COUPON_CODE_UPDATED_AT"
    }
}
```

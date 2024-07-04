# Event API Documentation

This documentation provides information about the Event API endpoints.

## Create Event

Create a new event.

### Request

- Method: POST
- Endpoint: `/create-event`

#### Request Body

| Parameter | Type   | Description       |
| --------- | ------ | ----------------- |
| shopId    | String | ID of the shop    |
| images    | Array  | Array of image URLs |

### Response

- Status Code: 201 (Created)

#### Response Body

```json
{
    "success": true,
    "event": {
        "_id": "event_id",
        "shop": "shop_id",
        "images": [
            {
                "public_id": "image_public_id",
                "url": "image_url"
            }
        ],
        "createdAt": "event_created_at",
        "updatedAt": "event_updated_at"
    }
}
```

## Get All Events

Get all events.

### Request

- Method: GET
- Endpoint: `/get-all-events`

### Response

- Status Code: 200 (OK)

#### Response Body

```json
{
    "success": true,
    "events": [
        {
            "_id": "event_id",
            "shop": "shop_id",
            "images": [
                {
                    "public_id": "image_public_id",
                    "url": "image_url"
                }
            ],
            "createdAt": "event_created_at",
            "updatedAt": "event_updated_at"
        }
    ]
}
```

## Get All Events of a Shop

Get all events of a specific shop.

### Request

- Method: GET
- Endpoint: `/get-all-events/:id`

#### Path Parameters

| Parameter | Type   | Description       |
| --------- | ------ | ----------------- |
| id        | String | ID of the shop    |

### Response

- Status Code: 200 (OK)

#### Response Body

```json
{
    "success": true,
    "events": [
        {
            "_id": "event_id",
            "shop": "shop_id",
            "images": [
                {
                    "public_id": "image_public_id",
                    "url": "image_url"
                }
            ],
            "createdAt": "event_created_at",
            "updatedAt": "event_updated_at"
        }
    ]
}
```

## Delete Event of a Shop

Delete an event of a specific shop.

### Request

- Method: DELETE
- Endpoint: `/delete-shop-event/:id`

#### Path Parameters

| Parameter | Type   | Description       |
| --------- | ------ | ----------------- |
| id        | String | ID of the event   |

### Response

- Status Code: 200 (OK)

#### Response Body

```json
{
    "success": true,
    "message": "Event Deleted successfully!"
}
```

## Get All Events (Admin)

Get all events (admin only).

### Request

- Method: GET
- Endpoint: `/admin-all-events`

### Response

- Status Code: 200 (OK)

#### Response Body

```json
{
    "success": true,
    "events": [
        {
            "_id": "event_id",
            "shop": "shop_id",
            "images": [
                {
                    "public_id": "image_public_id",
                    "url": "image_url"
                }
            ],
            "createdAt": "event_created_at",
            "updatedAt": "event_updated_at"
        }
    ]
}
```

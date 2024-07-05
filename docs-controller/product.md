# Product API Documentation

This documentation provides information about the Product API endpoints.

## Create Product

Create a new product.

### Request

- Method: POST
- Endpoint: `/create-product`

#### Request Body

| Parameter | Type   | Required | Description       |
| --------- | ------ | -------- | ----------------- |
| shopId    | string | Yes      | ID of the shop    |
| images    | array  | Yes      | Array of images    |

### Response

- Status Code: 201 - Created

#### Response Body

```json
{
    "success": true,
    "product": {
        "_id": "product_id",
        "name": "Product Name",
        "price": 10.99,
        "images": [
            {
                "public_id": "image_public_id",
                "url": "image_url"
            }
        ],
        "shop": {
            "_id": "shop_id",
            "name": "Shop Name"
        }
    }
}
```

## Get All Products of a Shop

Get all products of a shop.

### Request

- Method: GET
- Endpoint: `/get-all-products-shop/:id`

#### Path Parameters

| Parameter | Type   | Required | Description       |
| --------- | ------ | -------- | ----------------- |
| id        | string | Yes      | ID of the shop    |

### Response

- Status Code: 200 - OK

#### Response Body

```json
{
    "success": true,
    "products": [
        {
            "_id": "product_id",
            "name": "Product Name",
            "price": 10.99,
            "images": [
                {
                    "public_id": "image_public_id",
                    "url": "image_url"
                }
            ],
            "shop": {
                "_id": "shop_id",
                "name": "Shop Name"
            }
        }
    ]
}
```

## Delete Product of a Shop

Delete a product of a shop.

### Request

- Method: DELETE
- Endpoint: `/delete-shop-product/:id`

#### Path Parameters

| Parameter | Type   | Required | Description       |
| --------- | ------ | -------- | ----------------- |
| id        | string | Yes      | ID of the product |

### Response

- Status Code: 200 - OK

#### Response Body

```json
{
    "success": true,
    "message": "Product Deleted successfully!"
}
```

## Get All Products

Get all products.

### Request

- Method: GET
- Endpoint: `/get-all-products`

### Response

- Status Code: 200 - OK

#### Response Body

```json
{
    "success": true,
    "products": [
        {
            "_id": "product_id",
            "name": "Product Name",
            "price": 10.99,
            "images": [
                {
                    "public_id": "image_public_id",
                    "url": "image_url"
                }
            ],
            "shop": {
                "_id": "shop_id",
                "name": "Shop Name"
            }
        }
    ]
}
```

## Create New Review

Create a new review for a product.

### Request

- Method: PUT
- Endpoint: `/create-new-review`

#### Request Body

| Parameter | Type   | Required | Description       |
| --------- | ------ | -------- | ----------------- |
| user      | string | Yes      | ID of the user    |
| rating    | number | Yes      | Rating of the product (1-5) |
| comment   | string | Yes      | Comment for the product |
| productId | string | Yes      | ID of the product |
| orderId   | string | Yes      | ID of the order   |

### Response

- Status Code: 200 - OK

#### Response Body

```json
{
    "success": true,
    "message": "Reviewed successfully!"
}
```

## Get All Products (Admin)

Get all products (for admin).

### Request

- Method: GET
- Endpoint: `/admin-all-products`

### Response

- Status Code: 200 - OK

#### Response Body

```json
{
    "success": true,
    "products": [
        {
            "_id": "product_id",
            "name": "Product Name",
            "price": 10.99,
            "images": [
                {
                    "public_id": "image_public_id",
                    "url": "image_url"
                }
            ],
            "shop": {
                "_id": "shop_id",
                "name": "Shop Name"
            }
        }
    ]
}
```

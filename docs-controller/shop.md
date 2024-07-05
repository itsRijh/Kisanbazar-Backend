# Shop API Documentation

## Create Shop

- Endpoint: `/create-shop`
- Method: `POST`
- Description: Creates a new shop with the provided details.
- Request Body:
    - `name` (string): The name of the shop.
    - `email` (string): The email address of the shop.
    - `password` (string): The password for the shop.
    - `avatar` (string): The URL of the shop's avatar image.
    - `address` (string): The address of the shop.
    - `phoneNumber` (string): The phone number of the shop.
    - `zipCode` (string): The zip code of the shop.
- Response:
    - Status Code: `201`
    - Body:
        - `success` (boolean): Indicates if the shop was created successfully.
        - `message` (string): A message indicating the next steps for the shop owner.

## Activate Shop

- Endpoint: `/activation`
- Method: `POST`
- Description: Activates a shop using the activation token.
- Request Body:
    - `activation_token` (string): The activation token received via email.
- Response:
    - Status Code: `201`
    - Body:
        - `success` (boolean): Indicates if the shop was activated successfully.
        - `seller` (object): The details of the activated shop.

## Login Shop

- Endpoint: `/login-shop`
- Method: `POST`
- Description: Logs in a shop with the provided email and password.
- Request Body:
    - `email` (string): The email address of the shop.
    - `password` (string): The password for the shop.
- Response:
    - Status Code: `201`
    - Body:
        - `success` (boolean): Indicates if the login was successful.
        - `seller` (object): The details of the logged in shop.

## Get Shop

- Endpoint: `/getSeller`
- Method: `GET`
- Description: Retrieves the details of the authenticated shop.
- Response:
    - Status Code: `200`
    - Body:
        - `success` (boolean): Indicates if the retrieval was successful.
        - `seller` (object): The details of the shop.

## Logout Shop

- Endpoint: `/logout`
- Method: `GET`
- Description: Logs out the authenticated shop.
- Response:
    - Status Code: `201`
    - Body:
        - `success` (boolean): Indicates if the logout was successful.
        - `message` (string): A message indicating the logout status.

## Get Shop Info

- Endpoint: `/get-shop-info/:id`
- Method: `GET`
- Description: Retrieves the details of a shop by its ID.
- Request Parameters:
    - `id` (string): The ID of the shop.
- Response:
    - Status Code: `201`
    - Body:
        - `success` (boolean): Indicates if the retrieval was successful.
        - `shop` (object): The details of the shop.

## Update Shop Avatar

- Endpoint: `/update-shop-avatar`
- Method: `PUT`
- Description: Updates the avatar image of the authenticated shop.
- Request Body:
    - `avatar` (string): The URL of the new avatar image.
- Response:
    - Status Code: `200`
    - Body:
        - `success` (boolean): Indicates if the update was successful.
        - `seller` (object): The details of the updated shop.

## Update Seller Info

- Endpoint: `/update-seller-info`
- Method: `PUT`
- Description: Updates the information of the authenticated shop.
- Request Body:
    - `name` (string): The new name of the shop.
    - `description` (string): The new description of the shop.
    - `address` (string): The new address of the shop.
    - `phoneNumber` (string): The new phone number of the shop.
    - `zipCode` (string): The new zip code of the shop.
- Response:
    - Status Code: `201`
    - Body:
        - `success` (boolean): Indicates if the update was successful.
        - `shop` (object): The details of the updated shop.

## Get All Sellers (Admin Only)

- Endpoint: `/admin-all-sellers`
- Method: `GET`
- Description: Retrieves the details of all sellers (admin only).
- Response:
    - Status Code: `201`
    - Body:
        - `success` (boolean): Indicates if the retrieval was successful.
        - `sellers` (array): An array of seller objects.

## Delete Seller (Admin Only)

- Endpoint: `/delete-seller/:id`
- Method: `DELETE`
- Description: Deletes a seller by their ID (admin only).
- Request Parameters:
    - `id` (string): The ID of the seller to be deleted.
- Response:
    - Status Code: `201`
    - Body:
        - `success` (boolean): Indicates if the deletion was successful.
        - `message` (string): A message indicating the deletion status.

## Update Payment Methods (Seller Only)

- Endpoint: `/update-payment-methods`
- Method: `PUT`
- Description: Updates the payment methods of the authenticated seller.
- Request Body:
    - `withdrawMethod` (string): The new payment method for withdrawals.
- Response:
    - Status Code: `201`
    - Body:
        - `success` (boolean): Indicates if the update was successful.
        - `seller` (object): The details of the updated seller.

## Delete Withdraw Method (Seller Only)

- Endpoint: `/delete-withdraw-method`
- Method: `DELETE`
- Description: Deletes the withdrawal method of the authenticated seller.
- Response:
    - Status Code: `201`
    - Body:
        - `success` (boolean): Indicates if the deletion was successful.
        - `seller` (object): The details of the updated seller.

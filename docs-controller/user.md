# User API Documentation

## Create User

Create a new user.

**URL:** `/create-user`

**Method:** `POST`

**Request Body:**
```json
{
    "name": "John Doe",
    "email": "johndoe@example.com",
    "password": "password123",
    "avatar": "https://example.com/avatar.jpg"
}
```

**Response:**
```json
{
    "success": true,
    "message": "Please check your email: johndoe@example.com to activate your account!"
}
```

## Activate User

Activate a user account.

**URL:** `/activation`

**Method:** `POST`

**Request Body:**
```json
{
    "activation_token": "your_activation_token"
}
```

**Response:**
```json
{
    "success": true,
    "user": {
        "_id": "user_id",
        "name": "John Doe",
        "email": "johndoe@example.com",
        "avatar": "https://example.com/avatar.jpg"
    }
}
```

## Login User

Login a user.

**URL:** `/login-user`

**Method:** `POST`

**Request Body:**
```json
{
    "email": "johndoe@example.com",
    "password": "password123"
}
```

**Response:**
```json
{
    "success": true,
    "user": {
        "_id": "user_id",
        "name": "John Doe",
        "email": "johndoe@example.com",
        "avatar": "https://example.com/avatar.jpg"
    },
    "token": "your_jwt_token"
}
```

## Get User

Get user information.

**URL:** `/getuser`

**Method:** `GET`

**Response:**
```json
{
    "success": true,
    "user": {
        "_id": "user_id",
        "name": "John Doe",
        "email": "johndoe@example.com",
        "avatar": "https://example.com/avatar.jpg"
    }
}
```

## Logout User

Logout a user.

**URL:** `/logout`

**Method:** `GET`

**Response:**
```json
{
    "success": true,
    "message": "Logout successful!"
}
```

## Update User Info

Update user information.

**URL:** `/update-user-info`

**Method:** `PUT`

**Request Body:**
```json
{
    "email": "johndoe@example.com",
    "password": "password123",
    "phoneNumber": "1234567890",
    "name": "John Doe"
}
```

**Response:**
```json
{
    "success": true,
    "user": {
        "_id": "user_id",
        "name": "John Doe",
        "email": "johndoe@example.com",
        "avatar": "https://example.com/avatar.jpg",
        "phoneNumber": "1234567890"
    }
}
```

## Update User Avatar

Update user avatar.

**URL:** `/update-avatar`

**Method:** `PUT`

**Request Body:**
```json
{
    "avatar": "https://example.com/new_avatar.jpg"
}
```

**Response:**
```json
{
    "success": true,
    "user": {
        "_id": "user_id",
        "name": "John Doe",
        "email": "johndoe@example.com",
        "avatar": "https://example.com/new_avatar.jpg"
    }
}
```

## Update User Addresses

Update user addresses.

**URL:** `/update-user-addresses`

**Method:** `PUT`

**Request Body:**
```json
{
    "addressType": "Home",
    "addressLine1": "123 Main St",
    "addressLine2": "Apt 4B",
    "city": "New York",
    "state": "NY",
    "postalCode": "12345"
}
```

**Response:**
```json
{
    "success": true,
    "user": {
        "_id": "user_id",
        "name": "John Doe",
        "email": "johndoe@example.com",
        "avatar": "https://example.com/avatar.jpg",
        "addresses": [
            {
                "_id": "address_id",
                "addressType": "Home",
                "addressLine1": "123 Main St",
                "addressLine2": "Apt 4B",
                "city": "New York",
                "state": "NY",
                "postalCode": "12345"
            }
        ]
    }
}
```

## Delete User Address

Delete a user address.

**URL:** `/delete-user-address/:id`

**Method:** `DELETE`

**Response:**
```json
{
    "success": true,
    "user": {
        "_id": "user_id",
        "name": "John Doe",
        "email": "johndoe@example.com",
        "avatar": "https://example.com/avatar.jpg",
        "addresses": []
    }
}
```

## Update User Password

Update user password.

**URL:** `/update-user-password`

**Method:** `PUT`

**Request Body:**
```json
{
    "oldPassword": "old_password",
    "newPassword": "new_password",
    "confirmPassword": "new_password"
}
```

**Response:**
```json
{
    "success": true,
    "message": "Password updated successfully!"
}
```

## Get User Information

Get user information by user ID.

**URL:** `/user-info/:id`

**Method:** `GET`

**Response:**
```json
{
    "success": true,
    "user": {
        "_id": "user_id",
        "name": "John Doe",
        "email": "johndoe@example.com",
        "avatar": "https://example.com/avatar.jpg"
    }
}
```

## Get All Users (Admin)

Get all users (admin only).

**URL:** `/admin-all-users`

**Method:** `GET`

**Response:**
```json
{
    "success": true,
    "users": [
        {
            "_id": "user_id",
            "name": "John Doe",
            "email": "johndoe@example.com",
            "avatar": "https://example.com/avatar.jpg"
        },
        {
            "_id": "user_id",
            "name": "Jane Smith",
            "email": "janesmith@example.com",
            "avatar": "https://example.com/avatar.jpg"
        }
    ]
}
```

## Delete User (Admin)

Delete a user (admin only).

**URL:** `/delete-user/:id`

**Method:** `DELETE`

**Response:**
```json
{
    "success": true,
    "message": "User deleted successfully!"
}
}
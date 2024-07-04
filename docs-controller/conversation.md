This document outlines the API endpoints for managing conversations in your application. It uses the Express.js framework.

Requirements:

express: The web framework used for building the API.
Conversation: A model representing a conversation object (likely imported from ../model/conversation).
ErrorHandler: A custom error handling class (likely imported from ../utils/ErrorHandler).
catchAsyncErrors: Middleware for handling asynchronous errors (likely imported from ../middleware/catchAsyncErrors).
auth: Middleware for authentication (likely imported from ../middleware/auth). This includes functions:
isSeller: Checks if the user is a seller.
isAuthenticated: Checks if the user is authenticated.
Routes:

All routes are defined on an Express router object.

1. Create a New Conversation (POST /create-new-conversation):

This route allows authenticated users to create a new conversation.
Request Body:
groupTitle: The title of the conversation (string).
userId: The ID of the user creating the conversation (string).
sellerId: The ID of the seller involved in the conversation (string).
Middleware:
catchAsyncErrors: Handles any asynchronous errors that occur.
Response:
Status code:
201 (Created): Conversation created successfully.
Body:
success: Boolean indicating success (true).
conversation: The newly created conversation object.
2. Get All Seller Conversations (GET /get-all-conversation-seller/:id):

This route allows sellers to retrieve all their conversations.
Parameters:
:id: The ID of the seller (string).
Middleware:
isSeller: Ensures the user is a seller.
catchAsyncErrors: Handles any asynchronous errors that occur.
Response:
Status code:
201 (Created): Conversations retrieved successfully.
Body:
success: Boolean indicating success (true).
conversations: An array of conversation objects for the seller.
3. Get All User Conversations (GET /get-all-conversation-user/:id):

This route allows users to retrieve all their conversations.
Parameters:
:id: The ID of the user (string).
Middleware:
isAuthenticated: Ensures the user is authenticated.
catchAsyncErrors: Handles any asynchronous errors that occur.
Response:
Status code:
201 (Created): Conversations retrieved successfully.
Body:
success: Boolean indicating success (true).
conversations: An array of conversation objects for the user.
4. Update Last Message (PUT /update-last-message/:id):

This route allows updating the last message and its ID for a conversation.
Parameters:
:id: The ID of the conversation (string).
Request Body:
lastMessage: The updated last message content (string).
lastMessageId: The ID of the updated last message (string).
Middleware:
catchAsyncErrors: Handles any asynchronous errors that occur.
Response:
Status code:
201 (Created): Last message updated successfully.
Body:
success: Boolean indicating success (true).
conversation: The updated conversation object.
Error Handling:

Any errors that occur are caught by the catchAsyncErrors middleware and passed to an ErrorHandler class for a consistent error response format.

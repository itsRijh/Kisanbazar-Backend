# Conversation Model

The Conversation model represents a conversation in the Kisanbazar Backend application.

## Properties

- `groupTitle` (String): The title of the conversation group.
- `members` (Array): An array of members participating in the conversation.
- `lastMessage` (String): The content of the last message sent in the conversation.
- `lastMessageId` (String): The ID of the last message sent in the conversation.

## Timestamps

The Conversation model includes timestamps for the following events:

- `createdAt`: The date and time when the conversation was created.
- `updatedAt`: The date and time when the conversation was last updated.

## Usage

To use the Conversation model in your application, require it as follows:

```javascript
const Conversation = require("path/to/conversationModel");
```

You can then create, update, or query conversation objects using the provided methods of the Conversation model.

```
const conversation = new Conversation({
    groupTitle: "Sample Group",
    members: ["user1", "user2"],
    lastMessage: "Hello, how are you?",
    lastMessageId: "1234567890"
});

conversation.save()
    .then(savedConversation => {
        console.log("Conversation saved:", savedConversation);
    })
    .catch(error => {
        console.error("Error saving conversation:", error);
    });
```

```
Conversation.findOne({ groupTitle: "Sample Group" })
    .then(foundConversation => {
        console.log("Found conversation:", foundConversation);
    })
    .catch(error => {
        console.error("Error finding conversation:", error);
    });
```

```
Conversation.updateOne({ groupTitle: "Sample Group" }, { lastMessage: "New message" })
    .then(updatedConversation => {
        console.log("Updated conversation:", updatedConversation);
    })
    .catch(error => {
        console.error("Error updating conversation:", error);
    });
```

```
Conversation.deleteOne({ groupTitle: "Sample Group" })
    .then(deletedConversation => {
        console.log("Deleted conversation:", deletedConversation);
    })
    .catch(error => {
        console.error("Error deleting conversation:", error);
    });
```

```
Conversation.find()
    .then(allConversations => {
        console.log("All conversations:", allConversations);
    })
    .catch(error => {
        console.error("Error finding conversations:", error);
    });
```

Remember to replace `"path/to/conversationModel"` with the actual path to your Conversation model file.
```

Please note that this is just an example and you may need to modify it based on your specific requirements and project structure.
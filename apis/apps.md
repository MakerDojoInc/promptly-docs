---
title: Apps API
description: APIs to integrate with Apps
layout: default
parent: APIs
nav_order: 1
---

To integrate with Apps API, you'll need to have the AppID which can be obtained from the URL of the app. The API format for sending input to an App is:

```
curl -X POST https://trypromptly.com/api/apps/<AppID>/run \
    -H 'Content-Type: application/json' \
    -H 'Authorization: Token <PROMPTLY_TOKEN>' \
    -d '{"input": <INPUT_JSON>}'
```

Response Format
```
{
  "session": {
    "id": <SESSION_ID>
  },
  "output": {
    <APP_OUTPUT_JSON>
  }
}
```

Here, you need to replace <AppID> with the ID of the App you want to run, and <INPUT_JSON> with the JSON object containing the input values for the App. The Authorization header requires a PROMPTLY_TOKEN which is obtained by following the steps mentioned in the Promptly API documentation.

It's important to note that the input format for Apps is slightly different than for Endpoints. For example, if the input fields for an app are field_1 and field_2, the input JSON object should be in the following format:

```{"input":{"field_1":"value1","field_2":"value2"}}```

### Chat History
The session feature in Promptly allows you to store and retrieve chat history when using the Text-Chat processor. When you make a call to ```/api/apps/<app_id>/run``` with an input message, it returns the session object with a unique session ID.

To continue the conversation where it left off, you can make subsequent calls to ```/api/apps/<app_id>/run/<session_id>``` with the session ID included in the URL. This includes the chat history up to that point and allows the AI to better understand the context of the conversation and provide more accurate responses.

By using the session feature, you can improve the user experience for your customers and create more engaging chatbot interactions.
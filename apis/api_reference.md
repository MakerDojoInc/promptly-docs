---
title: Apps/Endpoints Integration Guide
layout: default
parent: APIs
nav_order: 1
---
# Promptly APIs Integration Guide

> **_NOTE:_** You will need to add your own API keys to use the platform for production deployments. You can get your own API keys from providers like [Open AI](https://openai.com/), [Hugging Face](https://huggingface.co/), [DreamStudio](https://dreamstudio.ai/) etc.,

Welcome to the integration guide for Promptly Endpoints and Apps APIs. Apps and Endpoints are the basic building blocks of the Promptly platform, which enable you to automate tasks by providing inputs and getting outputs.

With the help of APIs, you can easily integrate Promptly Endpoints and Apps with your own software applications. This guide provides detailed instructions on how to integrate with both the Endpoints API and the Apps API, so you can get started quickly.

### What are Endpoints and Apps?
Before we dive into the details, let's take a quick look at what Endpoints and Apps are:

Endpoints are individual processors that are designed to perform specific tasks. They can receive input, process it, and produce output. Endpoints are the basic building blocks of the Promptly platform.

Apps, on the other hand, are a series of connected endpoints that perform a larger task. An app can be composed of several endpoints that work together to accomplish a specific goal.

### Endpoints API

To integrate with Endpoints API, you'll need to have the EndpointID which can be obtained from the URL of the endpoint. The API format for sending input to an Endpoint is:

```
curl -X POST https://trypromptly.com/api/endpoints/<EndpointID> \
    -H 'Content-Type: application/json' \
    -H 'Authorization: Token <PROMPTLY_TOKEN>' \
    -d '{"template_values": <KEY_VALUE_JSON>}'
```

Here, you need to replace <EndpointID> with the ID of the Endpoint you want to send input to, and <KEY_VALUE_JSON> with the JSON object containing the input values. The Authorization header requires a PROMPTLY_TOKEN which is obtained by following the steps mentioned in the Promptly API documentation.

Response Format
```
{
  "id": "<ENDPOINT_ID>",
  "output": {
    "choices": [
      {
        "role": "<ROLE>",
        "content": "<RESPONSE_CONTENT>"
      }
    ]
  }
}
```
The response format for the `output` object may vary depending on the specific endpoint processor being used, but it typically includes a list of possible responses along with any relevant metadata or additional information

### Apps API
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
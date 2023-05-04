---
title: Endpoints API
description: APIs to integrate with Endpoints
layout: default
parent: APIs
nav_order: 2
---

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
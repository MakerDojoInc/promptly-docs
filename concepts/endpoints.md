---
title: Endpoint
description: Managed API processor instances
layout: default
parent: Concepts
nav_order: 3
---
## Endpoints

Endpoint is a specific instance of an API processor with a specific set of configuration parameters which can be used to invoke the API. Users can create multiple endpoints for the same API processor with different configuration parameters and can call them using their Promptly API key and the endpoint UUID. Endpoints abstracts the API parameters like prompts, model parameters etc., and provides a simple interface to invoke the API.

Using endpoints, users can version their prompts and model parameters, track their changes and performance across different versions. This allows users to easily manage them in production.
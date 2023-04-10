---
title: Playground
description: Iterate, test and debug your LLM APIs.
layout: default
parent: Promptly Pages
nav_order: 1
---

The Promptly Playground is a web-based interface that allows users to interact with various language models like OpenAI's GPT-3.5. In this document, we will provide an overview of the Playground's features and functionality.

## Getting Started
To access the Promptly Playground, [login](https://trypromptly.com/login) an simply navigate to the following URL in your web browser:

```
https://trypromptly.com/
```

## Interacting with API Backends
The Promptly playground provides a dropdown menu that allows users to select the API backend that they would like to interact with and a form to set API parameters and input. The following backends are currently supported:

| Backend | API Documentation |
| ------- | --- |
| OpenAI | [https://platform.openai.com/docs/api-reference](https://platform.openai.com/docs/api-reference) |
| Cohere | [https://docs.cohere.ai/reference/about](https://docs.cohere.ai/reference/about)         |
| StabiltiyAI | [https://api.stability.ai/docs](https://api.stability.ai/docs)             |

## Using the Playground's Features
The Playground provides several features that allow users to customize their interactions with the language models. These features include:
* **Model Selection**: Users can choose from a variety of language models supported by the API, e.g gpt3.5-turbo or gpt-4 for ChatGPT backend
* **API Input**: Users can provide a prompt to the API backend to generate a response. You can make use of template variable when specifying your inputs, this give you the flexibility to keep your prompt constant and only change the variable. For example, if you want to generate a response to the prompt "I am a {profession} and I like to {verb}." you can set the prompt to "I am a {{profession}} and I like to {{verb}}." and set the variable to "profession" and "verb" separately. The templated variable will be replaced with the template value you provide in the input form.
* **API Parameters**: Users can set parameters for the API backend, e.g. number of tokens to generate, temperature, etc.
* **Save Enpoint**: Once you are satisfied with the API response, you can save the endpoint to your account.  When you save an endpoint, its saves the input and the configuration parameter. Additionaly you can also specify a name and description for the endpoint. This will allow you to easily identify the endpoint later. Saved endpoints are versioned, every new save will create a new version of the endpoint. Saved endpoints help you to have a customized version of the vanilla APIs tailored to your usecases. 
* **Share prompts**: Create a prompt and share the prompt and results with other by clicking on the share button. This will create a sharable link that you can share with others.

## Advanced Usage
If you are interested in accessing your saved endpoints programmatically, you can do so by clicking on the **API** tab in the output section. The API always points the the latest live version of your endpoint. 
You can easily tweak the input prompt or configuration for your endpoint from the playground and save your endpoint. Mark your latest version as live and you are all set. Your application integrating the ednpoint via the endpoint will have your latest and greatest version of the endpoint, no code change required. 
Playground helps make prompt change management easy and seamless.


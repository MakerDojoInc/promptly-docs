---
title: Concepts
layout: default
nav_order: 2
---

## Concepts

### Application

An Application on Promptly is a high level abstraction that allows users to chain multiple LLM backends together to create complex workflows. Application is built using a simple form builder and can be used to generative AI applications like chatbots, summarizers, etc., Once an application is published, it will be available as a web app, chat widgets or as REST API that can be called from other services like [Zapier](https://zapier.com) for richer integrations.

#### Application Input Form
An application can have multiple inputs. This is the input that the application takes, these inputs will be presented as a form when the application renders as a web page or cann be passed in the request body when call ing the application as a REST API.
The input form currently accepts the following type of inputs:
- **String** : This is a simple text input field
- **Text** : This is a multi line text input field
- **Number** : This is a number input field
- **Boolean** : This is a checkbox input field
- **File** : This is a file input field
- **Select** : This is a select input field, you can specify the choices for this field in the Options box

#### Application Input Configuration
This section provides the ability to provide any additional configuration for the application. These configuration paramaters will changes depending on the application type. For example, if the application type is **Chatbot**, you can provide the following configuration parameteers, a **Welcome Message**, **Assistant Image**.



#### Application Processor
An application processor is a specific LLM backend that is used to process the input and generate the output. You capture your application specific business logic in this section. You can chain multiple processors together to create complex workflows. For example, you can use a processor to generate a text summary and then use another processor to generate an image from the summary.

#### Application Output
You can specify the output that needs to be shown to the user when the application is called. You can style your output message using [Markdown](https://www.markdownguide.org/cheat-sheet/). In your output you can specify placeholders, these placeholder values will be replaced with the actual values when the application is called. All the input values specified in the input form and processor input, configuration and output will be available as placeholders in the output.

### API Providers

An API provider on Promptly is a service that provides an API to generate text or images or any entity that provides API to perform certain tasks. For example, [Open AI](https://openai.com/), [Hugging Face](https://huggingface.co/), [DreamStudio](https://dreamstudio.ai/) etc., are some of the API providers that provide APIs to generate text and images using LLM models. [Promptly](https://trypromptly.com) is also one of the supported API providers that provides APIs to perform complex operations like summarizing texts, chatbots with data augmentation, etc.,

In the future, we will also be adding support for custom API providers which allows you to bring in your own API implementations to the platform

> We are constantly adding more API providers to the platform. If you would like to see a specific API provider on the platform, please let us know by reaching out to us at [contact@trypromptly.com](mailto:contact@trypromptly.com)

### API Backends

An API backend is a specific API provided by an API provider. For example, [Open AI](https://openai.com/) has multiple APIs like [completions](https://platform.openai.com/docs/api-reference/completions/), [chat](https://platform.openai.com/docs/api-reference/chat), [image generation](https://platform.openai.com/docs/api-reference/images) etc.,

API backend on Promptly defines the input format, output format and the configuration parameters that are required to invoke the API. Documentation for each API backend is available on the platform.

### Endpoints

Endpoint is a specific instance of an API backend with a specific set of configuration parameters which can be used to invoke the API. Users can create multiple endpoints for the same API backend with different configuration parameters and can call them using their Promptly API key and the endpoint UUID. Endpoints abstracts the API backend parameters like prompts, model parameters etc., and provides a simple interface to invoke the API.

Using endpoints, users can version their prompts and model parameters, track their changes and performance across different versions. This allows users to easily manage them in production.



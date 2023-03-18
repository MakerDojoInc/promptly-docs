---
title: Concepts
layout: default
nav_order: 2
---

## Concepts

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

### Apps

Promptly apps are high level abstracts that allow users to chain multiple LLM backends together to create complex workflows and applications. Apps are built using a no-code visual editor and can be used to generative AI applications like chatbots, summarizers, etc., Along with a visual editor, Promptly also provides a code editor to allow users to write custom code to extend the functionality of the apps. Apps can be deployed as web apps, chat widgets or as REST API that can be called from other services like [Zapier](https://zapier.com) for richer integrations.

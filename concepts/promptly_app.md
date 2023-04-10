---
title: Application
description: Automated workflow with LLM
layout: default
parent: Concepts
nav_order: 1
---
## Application

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

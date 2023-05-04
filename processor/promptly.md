---
title: Promptly Processors
description: Custom processors offered by Promptly
layout: default
parent: Processor
nav_order: 4
---

## Promptly Processors

### Text Chat Processor

The text chat processor makes it easy to develop chatbots on user provided data. It uses the ChatGPT processor and a datasource to restrict the chatGPT model to a specific domain. The text chat processor can be used to build chatbots for various domains such as customer support, sales, marketing, etc.

Checkout our [AI-powered Search and Summarization](/embeddings.html).

### URL Extractor
The URL Extractor processor in Promptly allows you to extract text from a webpage by providing a URL as input. This can be useful for tasks like summarizing an article or extracting key information from a webpage. The processor uses machine learning models to extract relevant text from the webpage and outputs it as plain text. You can then use this text as input for subsequent processors in your workflow. Simply provide the URL you want to extract text from as input and the processor will return the extracted text.


### File Extractor
The File Extractor processor in Promptly allows you to extract text from files provided in base64-encoded format. This can be useful when you need to extract text from a file before using it in subsequent steps of your workflow.

To use the File Extractor processor, you can either select a file from your computer or provide the base64-encoded file data directly. Once the file data is passed to the processor, it will extract the text from the file and make it available for use in subsequent steps.

### Datasource Search
The Datasource Search processor allows you to search for data within a dataset using an input provided by the user. The processor compares the input against the contents of the dataset and returns any matching documents.
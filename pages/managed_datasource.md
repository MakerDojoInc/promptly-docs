---
title: Data Store
description: Managed data store for your LLM apps. 
layout: default
parent: Promptly Pages
nav_order: 2
---

## Why do I need a data store?
Most LLM models are trained on public datasets like [OpenWebText](https://skylion007.github.io/OpenWebTextCorpus/), [GPT-3](https://arxiv.org/abs/2005.14165), [GPT-4](https://arxiv.org/abs/2005.14165) etc. These datasets are large and contain a lot of information but they might not be  relevant to your use case. 
For example, if you are building a chatbot for your store, you might want the chatbot to respond to questions  about your inventory, your return policy, etc. 
By combining the capabilities of Language Model frameworks with your custom data, you can create powerful and personalized AI applications. 


## Promptly Data Store
Promptly provides a managed data store for your LLM apps. You can simply upload your file and start using that data source in your LLM apps.
Promptly does the heavy lifting for you. We extract relevant text from the datasource, tokenize it and store it in a format that is optimized for LLM frameworks. 

## How to use the data store?
To use the data store, you need to create an account on [Promptly](https://trypromptly.com/login). Once you have logged in, you can click on the **data** icon in the sidebar. Upload your data source and start using it in your LLM apps.

## Supported data sources
1. CSV
2. PDF
3. Copy paste text
4. Urls: You can paste a list of urls and we will extract the text from those urls.
5. Sitemap: You can paste a sitemap url and we will extract the text from all the urls in the sitemap.
6. Youtube: You can paste a youtube video url and we will get the audio from the video and add the audio transcription as text. This source type uses OpenAI's Whisper API to transcribe the audio. You can read more about the Whisper API [here](https://openai.com/blog/whisper/).
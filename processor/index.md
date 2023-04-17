---
title: API Processor
description: LLM provider integrations like OpenAI, Cohere, StabilityAI
layout: default
has_children: true
nav_order: 4
---
## API Processor

An API processor is the smallest building block in the promptly ecosystem. You can think of a processor as a black box that takes in some input and does some processing on that input, returns some output. Each processor defines its input, output and the configuration parameters that are required to invoke the processor.
OpenAI's Completions API is modelled as a processor on Promptly. You can invoke the processor by passing in the prompt and the models parameters. The processor returns the completion as the output.
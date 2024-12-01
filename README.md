# Proxy Tuning GPT2 with political data 

## Overview
This repository shows an implementation of proxy-tuning for language models, inspired by the concept outlined in **Tuning Language Models by Proxy**. This project focuses on proxy-tuning GPT2 with data from the 2024 election. 

## What is proxy-tuning?
A technique for guiding large language models by leveraging smaller fine-tuned models as "experts" and untuned versions as "anti-experts". The difference in logits between the two smaller models guides the output of the larger language model. 

## Project Goals
1. Fine-tune a smaller model.
2. Guide larger model's predictions during run time.
3. Answer questions about the 2024 election.

# Model Card
## Uses
- Fine-tuning language models to answer domain-specific questions about election data.
- Steering larger language models with proxy-tuning techniques for better reponses.
- Research into fine-tuning and decoding methods
## Sources
- **Data:** https://github.com/fivethirtyeight/data/tree/master/polls
- **Code:** Developed using the Hugging Face transformers library and inspired from the Tuning Language Models by Proxy paper
- **Models:** Fine tuned diltilGPT2 and guided larger model GPT2.
## Permissions
- **Models:** Models are used under their respective Hugging Face licenses.

## Code Structure
'''
/data/ # Datasets used
/fine_tuned_model/  # Pretrained and fine-tuned model
fine_tuning.ipynb  # Script to get fine-tuned model
demo.ipynb # Proxy tuning and Gradio display 
'''

# Proxy Tuning GPT2 with political data 

## Overview
This repository shows an implementation of proxy-tuning for language models, inspired by the concept outlined in **Tuning Language Models by Proxy**. This project focuses on proxy-tuning GPT2 with data from the 2024 election. 

## What is proxy-tuning?
A technique for guiding large language models by leveraging smaller fine-tuned models as "experts" and untuned versions as "anti-experts". The difference in logits between the two smaller models guides the output of the larger language model. 

## Project Goals
1. Fine-tune a smaller model.
2. Guide larger model's predictions during run time.
3. Answer questions about the 2024 election.

## Methodology
1. M: pretrained GPT-2 model
2. M-: pretrained, untuned distilGPT-2 with same vocabulary as M
3. M+: M-, after fine-tuning on 2024 election data
4. α: Control term to manage how much influence smaller model has on M
![Screenshot 2024-12-02 at 10 11 00 AM](https://github.com/user-attachments/assets/1461c73d-e504-4c2d-a390-131b5944239e)


## Critical Analysis
### Limitations 
1. Lack of data about 2024 election.
2. Computing resources to fine tune the expert model.
#### What are the next steps?
1. Improved data set and fine-tuning.
2. Refine the Gradio demo to make it more accessible and user friendly.
3. Scaling up by using larger models such as GPT3 or GPT4.

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
```
/data/ # Datasets used
/fine_tuned_model/  # Pretrained and fine-tuned model
fine_tuning.ipynb  # Script to get fine-tuned model
demo.ipynb # Script for proxy tuning and Gradio display
README.md # Project documentation
```
## Resource Links
- "Tuning Language Models by Proxy": https://arxiv.org/abs/2401.08565
- Repo about proxy-tuning: https://github.com/gwendolynthompson/proxy-tuning
- Original repo about proxy-tuning: https://github.com/alisawuffles/proxy-tuning
- "The Power of Proxy Data and Proxy Networks for Hyper-Parameter Optimization": https://arxiv.org/abs/2107.05471
- "Improve LLMs With Proxy Tuning" https://lightning.ai/lightning-ai/studios/improve-llms-with-proxy-tuning
- "LoFT: Local Proxy Fine-tuning Improves Transferability to Large Language Model Attacks" https://openreview.net/forum?id=3ucOvX8WVu
- "CPT: Consistent Proxy Tuning for Black-box Optimization" https://www.researchgate.net/publication/381885086_CPT_Consistent_Proxy_Tuning_for_Black-box_Optimization
- Conversation on Reddit about the paper: https://www.reddit.com/r/LocalLLaMA/comments/19dg8pk/new_paper_proxytuning_an_efficient_alternative_to/


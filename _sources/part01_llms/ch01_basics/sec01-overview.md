
# Definition

First of all, what is a language model?  

```{admonition} Language Model
A language model is a model that learns patterns from language data.
```

Remember this definition does not imply any virtues we may want from language models, i.e., factual, responsible, or explainable. 

Ok, so - what is a large language model? 
Defining LLM is as impossible as defining jazz music 😉 (ok perhaps a bit easier.) Let me fail in this way:

```{admonition} Large Language Model
A large language model is language models that are large enough, usually with more than a billion parameters, to demonstrate zero-shot and few-shot abilities. 
```

See the table below and the trend. 

| Name                                 | Number of parameters | Birth year           |
|--------------------------------------|----------------------|----------------------|
| BERT (medium)                        | 0.047B               | 2018                 |
| BERT (base)                          | 0.110B               | 2018                 |
| BERT (large)                         | 0.340B               | 2018                 |
| BERT (xlarge)                        | 1.270B               | 2018                 |
| Some Google Translate models (LSTMs) | 0.160 - 0.380B       | 2016-2020 (estimate) |
| GPT-1                                | 0.117B               | 2018                 |
| GPT-2                                | 1.5B                 | 2019                 |
| GPT-3                                | 1.3 - 175B           | 2020                 |


BERT (xlarge){cite}`devlin2018bert` is over 1B, but it doesn't perform any zero-shot or few-shot abilities as it still remains to be a word and document embedding model.  

GPT-1 {cite}`radford2018improving` is way under 1B and didn't claim any few-shot or zero-show generalizeability (its title is *Improving language understanding by generative pre-training*.)  
Being 1.5B, GPT-2 {cite}`radford2019language` was suddenly too powerful that OpenAI famously said "[*Due to our concerns about malicious applications of the technology, we are not releasing the trained model*](https://openai.com/research/better-language-models)". And what was the title? *Language models are unsupervised multitask learners*.

A year later, GPT-3 {cite}`brown2020language` was present in a paper titled [*Language Models are Few-Shot Learners*](https://arxiv.org/abs/2005.14165).  

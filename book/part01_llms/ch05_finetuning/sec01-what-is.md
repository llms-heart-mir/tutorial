# Instruction Finetuning

## What is finetuning?


```{admonition} Finetuning a LLM
Finetuning a LLM is to continue training a LLM using additional, small but focused datasets. 
```
As opposed to the pretraining stage where billions of documents are used, during the finetuning stage, we usually use a small set of documents, say, a few thousands or perhaps hundreds of thousands.

During the finetuning stage, we wouldn't want to change the LLM's weights drastically. That's why we use a smaller learning rate, and parameter-efficient finetuning strategies such as LoRA {cite}`hu2021lora` work pretty well.

## Behavior Before Finetuning

We perform finetuning when we want an LLM to behave somewhat differently from text completion of documents.

Even with finetuning, it's still text completion. But the format and the content of the generated text can be steered during finetuning.

For example, text completion means just keep writing a document with a given prompt like this:

**User's prompt:**
> What is music information retrieval?

An LLM without finetuning would continue to complete a document like this. You may or may not like it.

**User's prompt + possible continuation 1 by LLM (not finetuned):**
> What is music information retrieval? It is defined as a research field where..

Okay, it sounds reasonable, although you might want it to answer you back directly.
However, due to the stochastic nature of LLM generation, it could get worse.

**User's prompt + possible continuation 2 by LLM (not finetuned):**
> What is music information retrieval? What is audio signal processing? What is information retrieval? What is machine learning? ..

..or way worse, since there are so many ways to write a document in a way you wouldn't find useful.

**User's prompt + possible continuation 3 by LLM (not finetuned):**
> What is music information retrieval? I don't know ¯\_(ツ)_/¯

Now you get it -- the goal of finetuning is **to tame an LLM** to steer how it continues to generate texts.

### Behavior After Finetuning

It magically follows your instruction! (Not really, but..)

**User's prompt**
> What is music information retrieval?

**What you see on ChatGPT, Claude, etc**
> You: What is music information retrieval?<br>
> LLM: Oh, music information retrieval (MIR) is an interdisciplinary field that deals with retrieving, analyzing, and organizing music-related data, such as audio recordings, musical scores, and metadata associated with music. The primary goal of MIR is to develop computational methods and systems that can effectively process, understand, and interact with music content.<br>

In reality, the model is still following what it learned via the next-token prediction.
So how does it somehow answer your question?
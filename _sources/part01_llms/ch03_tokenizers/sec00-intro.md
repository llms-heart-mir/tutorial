# Tokenizers

What is a token in language models?

```{admonition} Language Model
A token is the smallest meaningful unit of text for a language model.  
```

When you're mostly finetuning and using provided LLMs, it's easy to overlook the importance of understanding tokenizers, as you merely use them as given while making small changes to the model.

I beg to change this view. Tokenization is the very first step of text processing in LLMs. The current tokenization works pretty well, at least much better than the previous methods in the pre-LLM era. At the same time, many of the properties and limitations of LLMs come from the tokenization step.

Therefore, to understand LLMs, it is absolutely necessary to understand tokenizers - their mechanism, their training procedure, why the current tokenizers work in such a way, their pros and cons, etc.

I'll be brief. Watch Andrej Karpathy's [1-hr tutorial video on tokenizers](https://www.youtube.com/watch?v=zduSFxRajkE) if you want a deeper dive.
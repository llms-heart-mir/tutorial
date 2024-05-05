# Sub-word Tokenizers

Let's keep using the same example sentence.

```
"I'm instantiating a tokenizer for my LLMs"
```

GPT-4 tokenizer split the text as follows:

```
I / 'm / instant / iating / a / tokenizer / for / my / L/ LM / s
```

Compare this to word-based tokenizers.

- Sub-words are smaller.
  - It's better to split `I` + `'m` because they're smaller yet meaningful unit of text than `I'm`. 
  - Similarly, It's better to split `instant` + `iating` because they're smaller yet meaningful unit of text.
  - Same, `L` + `LM` + `s` > `LLMs`.
- Smaller units lead to **smaller vocab size**, hence better.

Indeed, GPT-4 uses their tokenizer named `cl100k_base`, whose vocab size is only 100k but can represent a lot of words than possibly a 1M-vocab word-based tokenizer. 

## Training Sub-word Tokenizers

is omitted in this book :p It's called "Byte-Pair Encoding" tokenizers, go study yourself! 

My lazy summary:
- As in the example above, all the current LLMs use some kind of sub-word tokenizers. 
- You need to train these sub-word tokenizers. It's not too computationally heavy to train tokenizers. 
- By also adopting the "byte fallback" property, out-of-vocabulary tokens are split into byte representation and passed to the LLMs. 
  - This remedy enables LLMs to also process multiple languages, although it makes the tokenized result too long for those non-primary languages.  

## Pros
- Sub-words are more efficient and effective than words

## Cons
- It still simply maps from texts through token indices to embeddings. This blocks the language model to understand anything before the tokenization step. 
  - For example, the model has little visibility to spellings of text. To be discussed later in this tutorial.    

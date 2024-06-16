# Sub-word Tokenizers

Let's keep using the same example sentence.

```
"I'm instantiating a tokenizer for my LLMs"
```

GPT-4 tokenizer splits the text as follows:

```
I / 'm / instant / iating / a / tokenizer / for / my / L/ LM / s
```

Compare this to word-based tokenizers:

- Sub-words are smaller.
  - It's better to split `I` + `'m` because they're smaller yet meaningful units of text than `I'm`.
  - Similarly, it's better to split `instant` + `iating` because they're smaller yet meaningful units of text.
  - Same, `L` + `LM` + `s` > `LLMs`.
- Smaller units lead to a **smaller vocab size**, hence better.

Indeed, GPT-4 uses their tokenizer named `cl100k_base`, whose vocab size is only 100k but can represent many more words than possibly a 1M-vocab word-based tokenizer.

## Training Sub-word Tokenizers

This is omitted in this book :p It's called "Byte-Pair Encoding" tokenizers, go study it yourself!

My lazy summary:
- As in the example above, all the current LLMs use some kind of sub-word tokenizers.
- You need to train these sub-word tokenizers. It's not too computationally heavy to train tokenizers.
- By also adopting the "byte fallback" property, out-of-vocabulary tokens are split into byte representations and passed to the LLMs.
  - This remedy enables LLMs to also process multiple languages, although it makes the tokenized result too long for those non-primary languages.

## Pros
- Sub-words are more efficient and effective than words.

## Cons
- It still simply maps from texts through token indices to embeddings. This blocks the language model from understanding anything before the tokenization step.
  - For example, the model has little visibility into the spellings of text. To be discussed later in this tutorial.
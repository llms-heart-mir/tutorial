# Word as a Token (Pre-LLM era)

## Word-based Tokenization

Take this sentence as an example:

```
"I'm instantiating a tokenizer for my LLMs"
```

How can we split this sentence into multiple tokens? 
I.e., How can we decide **the smallest meaningful unit** of this text?

The simplest way is to treat each word a token.

```
I'm / instantiating / a / tokenizer / for / my / LLMs
```

This means we'll have a lookup table of {word_index : embedding}. Hence, the example sentence would be converted to a sequence length of 7; and each word token would be represented by a vector.

This lookup table is trainable, and it's usually implemented using `nn.Linear`. If it's the llama-7B model, each word is converted to a 4096-dim vector. Initially they're random, but they're trained as a part of training the LLM. After successful training, each vector would represent the meaning of word in the vector space, somehow.

Note that we didn't train this tokenizer. We didn't train any tokenizer because all we have to do is split sentences by space ` `, which is trivial to implement. What we trained is the embedding layer.  


| Layer                             | Input                                      | Output                                |
|-----------------------------------|--------------------------------------------|---------------------------------------|
| nn.Linear (token embedding)       | (batch=*, sequence=2048, token_index: int) | (batch=*, sequence=2048, emb_dim=4096 |
| Self-Attention 1                  | (batch, sequence, emb_dim)                 | (batch, sequence, emb_dim)            |
| Self-Attention 2                  | (batch, sequence, emb_dim)                 | (batch, sequence, emb_dim)            |
| Self-Attention 3                  | (batch, sequence, emb_dim)                 | (batch, sequence, emb_dim)            |
| ...                               | (batch, sequence, emb_dim)                 | (batch, sequence, emb_dim)            |
| Self-Attention 31                 | (batch, sequence, emb_dim)                 | (batch, sequence, emb_dim)            |
| Self-Attention 32                 | (batch, sequence, emb_dim)                 | (batch, sequence, emb_dim)            |
| nn.Linear -> nn.Softmax (lm_head) | (batch, sequence, emb_dim)                 | (batch, sequence, n_token=50_000)     |


The problem is, in the real use-cases, a language model would need to process other sentences consists of other words, too. This means, to perfectly represent every word in the embedding layer, we need a very large embedding layers. 

Well, How many?

Let's say our target corpus is Wikipedia. According to [this repo](https://github.com/IlyaSemenov/wikipedia-word-frequency):

> Total unique words appearing at least in 3 articles: 2747823

There are whooping unique 2.7M words in English only, as of 2022. 

## Pros

- Different words convey different meanings. So it makes sense to treat it as a minimum unit.
- Perhaps not too different from how humans process natural languages.. perhaps. 
- Zero effort to train the tokenizer.

## Cons

- Huge vocabulary size leads to increased model complexity and memory requirements.
  - 3M vocab x 4096 dim = over 12B parameters = over 49GB if float32 is used. This embedding layer is already too big for most of the GPUs! 
- Inability to handle out-of-vocabulary (OOV) words, which are common in real-world text data.
  - Due to the memory issue, it's common to use most popular words under 1M or so. This means, due to the long tail distribution of words, OOV would occur often. 
- Lack of subword information, which can be useful for understanding morphological patterns and handling rare or unseen words.
  - E.g., it'd be better if `instantiating` can be split into `instantiat-` + `-ing`. Perhaps `LLMs` into `LLM` + `s`. `permutation` into `permute` + `-ate` + `-tion` or something. Something like that!  
- Difficulty in handling misspellings, slang, or other non-standard language elements.


These are why researchers came up with a better way: Sub-word tokenizers. 

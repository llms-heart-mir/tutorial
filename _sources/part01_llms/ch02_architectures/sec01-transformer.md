# Transformer

LLMs are usually built with the Transformer architecture {cite}`vaswani2017attention`.

There are almost nothing else but many **self-attention** layers in a Transformer-based LLM. For example, see this llama-1 6.7B architecture.

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


There are other ways for using self-attention layers. However, the recent LLMs are all alike. They are also called *decode-only transformers*.

## Token embedding

It is a simple embedding layer, i.e., a trainable look-up table mapping `token_index` --> `token_embedding`.  

## Self-attention

The strength of the Transformer comes from its unique self-attention mechanism. 
Since I'm not better than Andrej Karpathy at teaching, I'll send you to [his lecture video on GPT, 42:15](https://youtu.be/kCc8FmEb1nY?si=cBCRZAp5BWg5wirN&t=2535). 

Here's my very lossy tl;dr:
 - A self-attention layer maps a sequence of vector to another sequence of vector.
   - It does it by comparing every combination of all the time steps
     - So, it's memory-expensive, but powerful.

## LM Head

This is where the hidden vectors come back to the token space. 

Name: Aditya Singh | [LinkedIn](https://www.linkedin.com/in/adityasingh2022/) | [GitHub](https://github.com/adityasinghcoding)

# __Transformer from Scratch__

`Transformer`(transform/translate) helps in understanding real world meaning of the data by transforming the relations(important/priority-wise) w.r.t actual fundamental meaning. 
<br>___Note :___ Transformer acts as the model inside main model.

---
### __Components of Transformer__
1. ___Encoder Layer___
   - Input Embeddings
   - Positional Encoding
   - Self-Attention Layer
   - Feed Forward Network
2. ___Decoder Layer___
   - Masked Self-Attention
   - Encoder-Decoder Attention
   - Feed-Forward Network

---
**Attention**: It finds, measure, evaluate the relation of one word or any data with other data present in the batch/sequence/matrix. 
There are 2 types of Attentions:
- **Self Attention**: Evaluate connection/relation of each word/data. 
- **Multi Head Attention**: Multiple Self Attentions in parallel, to evaluate complex relations between entities(data).
--- 
### __Architecture of Transformers__
#### __Encoder Layer__
- **Input** (Data in Vector; Embedding of words)
- **Positional Encoding** (Metadata of data order with sine/cosine functions)
- **Self Attention Layer** (Relation capturing & evaluation or in technical terms: establishing weights)
   - $Attention(Q,K,V) = softmax\left(\frac{QK^T}{\sqrt{d_k}}\right)V$
      - _Q, K, V:_ Query, Key, Value
      - ${QK^T}$: Compute Scores/Interaction with others.
      - V: Vectors. 
   - $\sqrt{d_k}$: Fixes large dot products causing gradient issues.
- __Feed-Forward Network__ (Simple Neural Network)

#### __Decoder Layer__
- __Masked-Self Attention__ (Hiding future tokens during training)
- __Encoder-Decoder Attention__ (___Q___ from Decoder, ___K & V___ from Encoder. Encoder output used to focus on relevant input parts)

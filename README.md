Name: Aditya Singh | [LinkedIn](https://www.linkedin.com/in/adityasingh2022/) | [GitHub](https://github.com/adityasinghcoding)

# **Transformer from Scratch**

`Transformer`(transform/translate) helps in understanding real world meaning of the data by transforming the relations(important/priority-wise) w.r.t actual fundamental meaning.
<br>**_Note :_** Transformer acts as the model inside main model.

---

### **Components of Transformer**

1. **_Encoder Layer_**
   - Input Embeddings
   - Positional Encoding
   - Self-Attention Layer
   - Feed Forward Network
2. **_Decoder Layer_**
   - Masked Self-Attention
   - Encoder-Decoder Attention
   - Feed-Forward Network

---

**Attention**: It finds, measure, evaluate the relation of one word or any data with other data present in the batch/sequence/matrix.
There are 2 types of Attentions:

- **Self Attention**: Evaluate connection/relation of each word/data.
- **Multi Head Attention**: Multiple Self Attentions in parallel, to evaluate complex relations between entities(data). Head refers to the attention mechanism.

---

### **Architecture of Transformers**

#### **Encoder Layer**

- **Input** (Tokens/Embedding are the raw input to the Transformer.)
  Token's embedding transformed/split into 3 vectors: Q, K, V. Each token has its own Q, K, V.
- **Positional Encoding** (Metadata of data order with sine/cosine functions)
- **Self Attention Layer** (Relation capturing & evaluation or in technical terms: establishing weights)
  - $Attention(Q,K,V) = softmax\left(\frac{QK^T}{\sqrt{d_k}}\right)V$ <br>_Softmax(Sum to 1) is used to normalize the data(scores) & to convert scores to probability distribution._
    - _Q, K, V:_ Query, Key, Value
    - ${QK^T}$: Compute Scores/Interaction with others. <br>_Represents the strength of attention._
    - _V_: Value vectors, Dynamic dictionary. <br>_It contains content/dictionary/data which is linked with Q & K through multiplication helping in translating the relation in final understanding/output(placement of word). V helps in understanding the context of the language._
  - $\sqrt{d_k}$: Fixes large dot products causing gradient issues. </br> ${d_k}$ refers to the dimension of keys.<br>**_"d"_** is the dimensionality.
- **Feed-Forward Network** (Simple Neural Network)

#### **Decoder Layer**

- **Masked-Self Attention** (Hiding future tokens during training)
- **Encoder-Decoder Attention** (**_Q_** from Decoder, **_K & V_** from Encoder. Encoder output used to focus on relevant input parts)

---

### How **Q, K, V** Works in Transformers:

1.  **Input Tokens** → Projected into **Keys (K)** and **Values (V)**.
    - Think: Each token writes its **data (V)** and a **label (K)** into a dictionary.
2.  **Queries (Q)** "search" this dictionary by comparing **Q** to all **Ks**.
3.  The best-matching **Ks** (highest attention scores) retrieve their corresponding **Vs**.
4.  The output is a **weighted blend** of the retrieved **Vs**.

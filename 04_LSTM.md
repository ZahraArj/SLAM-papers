
<!---
Started to write on Sep 7 2021
Zahra
-->

## RNN
![image](https://user-images.githubusercontent.com/46463022/141521250-77504bf5-e44e-4746-8217-d5140d2a3976.png)

problem: RNNs become very ineffective when the gap between the relevant information and the point where it is needed become very large. That is due to the fact that the information is passed at each step and the longer the chain is, the more probable the information is lost along the chain.

## [LSTM](https://colah.github.io/posts/2015-08-Understanding-LSTMs/)
- Seq2Seq models consist of an Encoder and a Decoder
- **The output sequence can be in another language, symbols, a copy of the input, etc.**
  - Recurrent Neural Networks: 
    - They are networks with loops in them, allowing information to persist.  
      <img src="https://user-images.githubusercontent.com/46463022/132416289-1753870a-49a0-4a55-8ef9-b19ab83b855b.png" width="300"> 
      
      <img src="https://user-images.githubusercontent.com/46463022/132416477-f92372bb-5f79-4ea1-b2cb-6050954e3639.png" width="400">  

  - LSTM Networks  
      - Up: cell state
      - Down: Hidden state 
      <img src="https://user-images.githubusercontent.com/46463022/132416795-f0adf789-706a-4d86-93d1-e0e58ce2fecc.png" width="400">  
      
      |Name|Step-by-Step LSTM Walk Through|Description|
      | ------------- | ------------- | ------------- |
      |Forget gate layer|<img src="https://user-images.githubusercontent.com/46463022/132417332-a8524af1-4885-4718-8ca7-22543b9b2857.png" width="400">|
      |Input gate layer|<img src="https://user-images.githubusercontent.com/46463022/132417587-b1cf48ff-c00e-42e8-a07a-1e1dfdac6aaf.png" width="400">|forget layer for input/ Tanh: [-1,1] which information is important|
      |Calculate the cell state|<img src="https://user-images.githubusercontent.com/46463022/132417829-f353abb3-c06b-468c-ab9e-d990dfc0cee7.png" width="400">| dropping values/ input gate|
      |Output gate layer|<img src="https://user-images.githubusercontent.com/46463022/132417857-51e555db-79ff-4154-bbc6-8689078d170c.png" width="400">|
      
      
 ## [Transformer]
 * Set Transformer: A Framework for Attention-based Permutation-Invariant Neural Networks. (ex. LSTM)
 * Seq2Seq: an Encoder and a Decoder. maps it into a higher dimensional space (n-dimensional vector). 
 * A very basic choice for the Encoder and the Decoder of the Seq2Seq model is a single LSTM for each of them.
 * The attention-mechanism looks at an input sequence and decides at each step which other parts of the sequence are important.
 * The attention-mechanism looks at an input sequence and decides at each step which other parts of the sequence are important.
 * But it does not imply any Recurrent Networks (GRU, LSTM, etc.)
 * They proved that an architecture with only attention-mechanisms without any RNN (Recurrent Neural Networks) can improve on the results in translation task and other tasks! 
   ![image](https://user-images.githubusercontent.com/46463022/141361806-01a5d499-b21c-4865-975d-ddb4589bb9a9.png)



<!---
Started to write on Sep 7 2021
Zahra
-->

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
       

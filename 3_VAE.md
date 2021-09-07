<!---
Started to write on Sep 7 2021
Zahra
-->


##[VAE](https://medium.com/analytics-vidhya/mathematical-prerequisites-for-understanding-autoencoders-and-variational-autoencoders-vaes-8f854025390e)
  - The basic idea behind the VAE proposed by Kingma et al in 2013 is that instead of mapping an input to a fixed vector, the input is mapped to a distribution.
  - The only fundamental difference between an autoencoder and a variational autoencoder is that the bottleneck of the VAE is continuous and replaced by two separate vectors.
 
 <img width="700" alt="vae-gaussian" src="https://user-images.githubusercontent.com/46463022/132400632-0cb86cc9-1dc6-4753-a6e0-8c42844be46c.png"> 
 
 - Autoencoder Loss Function:  
   ![a](https://user-images.githubusercontent.com/46463022/132401375-57ac1f2a-8b5e-4269-b873-225bf2827aab.png)
 - VAE Loss Function (Reconstruction loss + KL divergence)
   ![a](https://user-images.githubusercontent.com/46463022/132401511-d341c92c-2378-45e6-8fda-d330f4e7279f.png) 
   1. The reconstruction loss
     - Expectation of Random variable X i.e E(x): The expected value of a random variable is a weighted average of all the possible values of X that it can take
      ![](https://user-images.githubusercontent.com/46463022/132405164-3a9a293e-c3c6-4b59-9c7b-189ac0c4ad65.png)

   2. The regularizer which is essentially a KL divergence between the encoder’s distribution and the latent space.



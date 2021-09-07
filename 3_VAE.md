<!---
Started to write on Sep 7 2021
Zahra
-->

## [VAE](https://medium.com/analytics-vidhya/mathematical-prerequisites-for-understanding-autoencoders-and-variational-autoencoders-vaes-8f854025390e)
  - The basic idea behind the VAE proposed by Kingma et al in 2013 is that instead of mapping an input to a fixed vector, the input is mapped to a distribution.
  - The only fundamental difference between an autoencoder and a variational autoencoder is that the bottleneck of the VAE is continuous and replaced by two separate vectors.
 
 <img width="700" alt="vae-gaussian" src="https://user-images.githubusercontent.com/46463022/132400632-0cb86cc9-1dc6-4753-a6e0-8c42844be46c.png">
 
 ### Loss Function
 - Autoencoder Loss Function:  
   ![a](https://user-images.githubusercontent.com/46463022/132401375-57ac1f2a-8b5e-4269-b873-225bf2827aab.png)
 - VAE Loss Function (Reconstruction loss + KL divergence)
   ![a](https://user-images.githubusercontent.com/46463022/132401511-d341c92c-2378-45e6-8fda-d330f4e7279f.png) 
   1. The reconstruction loss
     - Expectation of Random variable X i.e E(x): The expected value of a random variable is a weighted average of all the possible values of X that it can take. (this concept is similar to the mathematical average.)   
      ![](https://user-images.githubusercontent.com/46463022/132405164-3a9a293e-c3c6-4b59-9c7b-189ac0c4ad65.png)  

   2. The regularizer which is essentially a KL divergence between the encoder’s distribution and the latent space.
     - KL Divergence (D_KL): Kulback-Leibler Divergence (D_KL for short)  
      ![](https://user-images.githubusercontent.com/46463022/132405542-7540d1eb-3708-4aad-861a-1fb4d0f7884a.png)
  ### Gaussian Trick
  - Gaussian tricks: Decoder will sample z from q(z|x), The problem here is that backprop will not be able to flow throgh this random node:  
    <p align="center"> 
      <img src="https://user-images.githubusercontent.com/46463022/132406135-3eb944bf-4994-4dbb-a982-728225043508.png" width="400">
    </p>
  - [Figure: A training-time variational autoencoder implemented as a feedforward neural network, where P(X|z) is Gaussian. Left is without the “reparameterization trick”, and right is with it. Red shows sampling opera- tions that are non-differentiable. Blue shows loss layers. The feedforward behavior of these networks is identical, but backpropagation can be applied only to the right network.](https://arxiv.org/pdf/1606.05908.pdf) 
   <p align="center"> 
      <img src="https://user-images.githubusercontent.com/46463022/132412226-b2443581-5023-421f-a2e4-e6172386447e.png" width="500">  
   </p> 
            








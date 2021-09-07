# References



<!---
Started to write on Sep 3 2021
Zahra
-->

 
## Pose Graph Papers
 1. [2013: Information fusion in navigation systems via factor graph based incremental smoothing](https://www.cc.gatech.edu/~dellaert/pubs/Indelman13ras.pdf)
 2. [2018: Laser-visual-inertial Odometry and Mapping with High Robustness and Low Drift](https://www.researchgate.net/publication/326352534_Laser-visual-inertial_Odometry_and_Mapping_with_High_Robustness_and_Low_Drift)
 3. [2020: LIO-SAM: Tightly-coupled Lidar Inertial Odometry via Smoothing and Mapping](https://arxiv.org/pdf/2007.00258.pdf)
      - Proposing LiDAR odometry factor
      - Loop Closure factor
      - Lidar/IMU/GPS
<img src="https://user-images.githubusercontent.com/46463022/132263667-32ac0a70-3019-40ec-9ed0-8d4cf09738da.png">
      <br/>

 4. [2021: LVI-SAM: Tightly-coupled Lidar-Visual-Inertial Odometry via Smoothing and Mapping](https://arxiv.org/pdf/2104.10831.pdf)
      - Lidar/IMU/GPS/Vision
 <img src="https://user-images.githubusercontent.com/46463022/132414003-f0e772fc-64dc-4bed-b40b-0c5138a0b221.png">
      <br/>

 

<br/>
<br/>




## Pose Graph 
source: [hal](http://people.binf.ku.dk/~thamelry/MLSB08/hal.pdf)
 | Markov Chain | Factor Graph  |
:-------------------------:|:-------------------------:
|![](https://user-images.githubusercontent.com/46463022/132266002-c2df2813-07e8-434b-aa14-ac17885b973e.png)|![](https://user-images.githubusercontent.com/46463022/132266011-e1b4e8a0-9bb6-44b5-9019-ef8e04eaceab.png)|
|![](https://user-images.githubusercontent.com/46463022/132265964-c0fb3e49-e1f6-407b-884c-51ad060520a9.png) | ![](https://user-images.githubusercontent.com/46463022/132265982-a8351aba-118e-4a9f-bbc6-bc0c9d92924d.png)|



   - The maximum a posteriori (MAP) estimate is given by x= argmax p(x|z).  
   - x: is all the states (that we want to get)  
   - z: all the sensor measurmnets 
   <p align="center"> 
    <img src="https://user-images.githubusercontent.com/46463022/132265095-32d04d65-bcb6-45ef-a10b-e19902df3e49.png">  
   </p>
   
   
```ruby
   Σ can come from VAE
```
   
## [iSAM2](https://www.cs.cmu.edu/~kaess/pub/Kaess12ijrr.pdf)

  | Name | Equation  |
  :-------------------------:|:-------------------------:
  | A factor graph is a bipartite graph | ![](https://user-images.githubusercontent.com/46463022/132388495-9652dd14-8ddd-4f5d-84f3-04c022727655.png)|
  | Factor nodes | ![](https://user-images.githubusercontent.com/46463022/132388603-4e803658-27de-42cb-be14-e46351b18458.png)|
  | Variable nodes | ![](https://user-images.githubusercontent.com/46463022/132388686-83b7b068-f1b2-4cc7-9578-9bcb8cdebd33.png)|
  | Edges | ![](https://user-images.githubusercontent.com/46463022/132388775-b6c8230a-4353-4319-837b-a5d980d50a7d.png)|
  | A factor graph G defines the factorization of a function f (Θ) as:|![](https://user-images.githubusercontent.com/46463022/132388924-83c321eb-708c-433e-bb60-4a89022daaf7.png)|
  |  (where Θi is the set of variables θ j adjacent to the factor fi, and independence relationships are encoded by the edges eij)|
  | Goal is to find the variable assignment Θ∗ that maximizes f: |![](https://user-images.githubusercontent.com/46463022/132391432-dd54acbf-b4cc-45df-83f1-ee181fdd2df1.png)|
  | Assuming Gaussian measurement models: (h: measurment fun., z: measurmnet) | ![](https://user-images.githubusercontent.com/46463022/132391721-1cd8a93b-7606-4056-a494-5b9cb54c3264.png)|
  | Corresponds to the nonlinear least-squares criterion| ![](https://user-images.githubusercontent.com/46463022/132391848-495f42cf-381b-4e93-b679-00d9827abaac.png)|
  |Squared Mahalanobis distance with covariance matrix Σ |![](https://user-images.githubusercontent.com/46463022/132391942-4f06e4c6-1327-4f02-b171-54ebd5f264a0.png)|
  |The Mahalanobis distance is a measure of the distance between a point P and a distribution D. It is a multi-dimensional generalization of the idea of measuring how many standard deviations away P is from the mean of D|
  | In practice one typically considers a linearized version of problem (min)|
  








   
## Probability
Let Y be N(μ,σ2), the normal distrubution with parameters μ and σ2.
 - The density function of Y is   
 ![Screenshot from 2021-09-07 12-52-24](https://user-images.githubusercontent.com/46463022/132383632-bd81dfdb-9918-4075-947a-504ed85c60bc.png)  
 - Probability for a distribution is associated with the area under the curve for a particular range of values  
   ![gmz9453x54414z3108007](https://user-images.githubusercontent.com/46463022/132385692-9a02b388-dc49-4eab-b2bb-0331ea590881.gif)
 - The n-th central moment of Y is  
 ![Screenshot from 2021-09-07 13-04-52](https://user-images.githubusercontent.com/46463022/132383800-a9fc8c62-2b57-424c-9750-17177699d925.png)

 - If the function is a probability distribution, then the first moment is the expected value, the second central moment is the variance, the third standardized moment is the skewness  
  ![Screenshot from 2021-09-07 13-06-44](https://user-images.githubusercontent.com/46463022/132384013-eab42b2a-ff56-4ced-bc66-3b31d9b410ea.png)

   
## Probability vs. Likelihood
 - Probability is the percentage that a success occur. 
 - Likelihood is the probability (conditional probability) of an event (a set of success) occur by knowing the probability of a success occur.
   <p align="center"> 
    <img src="https://user-images.githubusercontent.com/46463022/132373331-58fc126b-6eb6-4561-a219-501574f1a5cd.png" width="500">
   </p>


## Marginalisation
- Marginalisation is a method that requires summing over the possible values of one variable to determine the marginal contribution of another.   
- Marginalization is a process of summing a variable X which has a joint distribution with other variables like Y, Z, and so on. Considering 3 random variables, we can mathematically express it as  
     ![](https://user-images.githubusercontent.com/46463022/132374994-1618b69e-2052-4294-a31d-2738bc325aad.png)
     
![](https://user-images.githubusercontent.com/46463022/132375559-52a81bfb-1497-48eb-a73a-bb27321b0378.png)
   



  
## Maximization
![](https://user-images.githubusercontent.com/46463022/132375580-f51b8af6-de77-4f52-aa20-95872d5e2c25.png)




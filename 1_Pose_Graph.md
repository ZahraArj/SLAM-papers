# References



<!---
Started to write on Sep 3 2021
Zahra
-->

 
### Pose Graph Papers
 1. [2013: Information fusion in navigation systems via factor graph based incremental smoothing](https://www.cc.gatech.edu/~dellaert/pubs/Indelman13ras.pdf)
 2. [2018: Laser-visual-inertial Odometry and Mapping with High Robustness and Low Drift](https://www.researchgate.net/publication/326352534_Laser-visual-inertial_Odometry_and_Mapping_with_High_Robustness_and_Low_Drift)
 3. [2020: LIO-SAM: Tightly-coupled Lidar Inertial Odometry via Smoothing and Mapping](https://arxiv.org/pdf/2007.00258.pdf)
      - Proposing LiDAR odometry factor
<img src="https://user-images.githubusercontent.com/46463022/132263667-32ac0a70-3019-40ec-9ed0-8d4cf09738da.png">
      <br/>

 4. [2021: LVI-SAM: Tightly-coupled Lidar-Visual-Inertial Odometry via Smoothing and Mapping](https://arxiv.org/pdf/2104.10831.pdf)

<br/>
<br/>


## Pose Graph 
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
   
## Probability vs. Likelihood
 - Probability is the percentage that a success occur. 
 - Likelihood is the probability (conditional probability) of an event (a set of success) occur by knowing the probability of a success occur.
<img src="https://user-images.githubusercontent.com/46463022/132373331-58fc126b-6eb6-4561-a219-501574f1a5cd.png width= "200">


## What is marginalisation
Marginalisation is a method that requires summing over the possible values of one variable to determine the marginal contribution of another. 


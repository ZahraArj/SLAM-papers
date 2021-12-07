
   <!---
Started to write on Sep 9 2021
Zahra
-->

## [MLE/MAP and Bayesian inference](https://towardsdatascience.com/mle-map-and-bayesian-inference-3407b2d6d4d9)
* Given the observed data D, estimations of a probabilistic model’s parameter θ by MLE and MAP are the following.
![image](https://user-images.githubusercontent.com/46463022/145089271-986aa1e5-bdcf-40fc-b609-ab537c22ce75.png)
![image](https://user-images.githubusercontent.com/46463022/145092128-0769f200-dd48-4bac-9b49-18318444f82b.png)

* MLE gives you the value which maximises the Likelihood P(D|θ). And MAP gives you the value which maximises the posterior probability P(θ|D). As both methods give you a single fixed value, they’re considered as point estimators.
* If a prior probability is given as part of the problem setup, then use that information (i.e. use MAP). If no such prior information is given or assumed, then MAP is not possible, and MLE is a reasonable approach.
* Bayesian inference fully calculates the posterior probability distribution, as below formula. Hence the output is not a single value but a probability density function (when θ is a continuous variable) or a probability mass function (when θ is a discrete variable).
![image](https://user-images.githubusercontent.com/46463022/145089407-5a6d635c-b04b-4b05-b30f-9bb3fb62da90.png)

**This is the difference between MLE/MAP and Bayesian inference. MLE and MAP returns a single fixed value, but Bayesian inference returns probability density (or mass) function.


## [Lie Algebras](https://www.math.uni-hamburg.de/home/wockel/teaching/data/cohomology_of_lie_algebras_imani.pdf)  
[Basics of Classical Lie Groups: TheExponential Map, Lie Groups, and Lie Algebras](https://www.cis.upenn.edu/~cis610/geombchap14.pdf)  
[Lie groups and Lie algebras](http://math.uchicago.edu/~womp/2001/lie.pdf)  
[A good source](http://jde27.uk/lgla/index.html)

- The wedge operator (·)∧ : Rn → g maps a column matrix to the matrix Lie algebra. 
- The “vee” operator (·)∨ : g→ Rn maps an element of the matrix Lie algebra to a column matrix.
- The exponential map exp(·) : g→ G maps an element of the matrix Lie algebra to the matrix Lie group, and is computed using the matrix exponential.
- The logarithmic map ln(·) : G → gmaps an element of the matrix Lie group to the matrix Lie algebra, and is computed by the matrix logarithm.  

<br/>

- **Theorem:** There is an equivalence between the category of complex simply connected Lie groups and category of complex Lie algebras.
### Lie groups  
![Screenshot from 2021-09-25 17-46-07](https://user-images.githubusercontent.com/46463022/134786733-8acdce12-2474-49f7-b60f-c8ac97721aec.png)
![Screenshot from 2021-09-26 12-29-38](https://user-images.githubusercontent.com/46463022/134816068-b4967832-d31a-42c2-b843-aaf61499b5f6.png)

![Screenshot from 2021-09-26 14-17-43](https://user-images.githubusercontent.com/46463022/134819483-ffa72148-832a-4a8e-8b75-48abb59ca5ba.png)
![Screenshot from 2021-09-26 14-19-43](https://user-images.githubusercontent.com/46463022/134819527-e23a83e2-e34b-452f-800a-c02ccfae11c4.png)


### Lie algebras
   - Each Lie group has a corresponding Lie Algebra
   - Lie Algebra is a local property of Lie Group
![Screenshot from 2021-09-25 17-45-11](https://user-images.githubusercontent.com/46463022/134786719-235762d9-34ef-42b2-8efa-738e2eb77503.png)  
  The Lie algebra of the rotation group SO(3) consists of antisymmetric 3x3 matrices, which must have the form:


  ![Screenshot from 2021-09-25 18-01-12](https://user-images.githubusercontent.com/46463022/134786964-458b9cf1-8367-4d54-9d40-bb1cc8fd8d0a.png)  
  By the way, the elements of the Lie algebra so(3) are usually represented by the angular velocity ω⃗ =(ω1,ω2,ω3) such that multiplication becomes the cross product: 
  ![Screenshot from 2021-09-25 18-01-28](https://user-images.githubusercontent.com/46463022/134786973-5a39323f-1b5b-483b-8ec3-3640f8ef702c.png)



## [Exponential map](https://math.stackexchange.com/questions/999515/meaning-of-exponential-map)
   The idea of an exponential is the continuous compounding of small actions.

## [SE(3)](https://rock-learning.github.io/pytransform3d/transformations.html)
   The group of all transformations in the 3D Cartesian space is SE(3) (SE: Special Euclidean group). Transformations consist of a rotation and a translation. Those can be represented in different ways just like rotations can be expressed in different ways.  
   All transformation matrices form the special Euclidean group SE(3). 
   [U of Pennsylvania](https://www.seas.upenn.edu/~meam620/slides/kinematicsI.pdf)
 <p align="center">
   <img src="https://user-images.githubusercontent.com/46463022/132751832-1101fca9-34db-48e9-970d-e0b155892fc1.png" width="500">
   <img src="https://user-images.githubusercontent.com/46463022/134244626-0f3364f0-b8d2-4297-83bd-0305029d5756.png" width="500">

 </p>
## SO(3)
The group of all rotations about the origin of three-dimensional Euclidean space R^3 under the operation of composition.

## Exponential Coordinates  
   Any transformation (rotation and translation) can be expressed by a motion along a screw axis.      
    
<img src="https://user-images.githubusercontent.com/46463022/132752705-5a27a1c4-4e18-4c81-90c3-5bdf29ea7a48.png" width="300">  

we can compute the screw axis from screw parameters (q, s, h) as:
<img align="right" width="200"  src="https://user-images.githubusercontent.com/46463022/132754648-6750bee9-b32a-4837-9695-6a269f518964.png">    

By multiplication with an additional parameter theta we can then define a complete transformation through its exponential coordinates:  
<img align="right" width="200" src="https://user-images.githubusercontent.com/46463022/132753770-14b46a46-881c-4315-8e78-ff9933e621ce.png">

<br/>
<br/>
<br/>

## [TDoA vs.TWR](https://www.mdpi.com/1424-8220/18/6/1875)  

TDoA: TDoA-based localization computes position estimates using the arrival time difference of signals from multiple anchors
<img align="right" width="400" src="https://user-images.githubusercontent.com/46463022/132772005-229411ec-96fa-449d-b691-c6df1db1b59a.png" />   
<img align="left" width="400" src="https://user-images.githubusercontent.com/46463022/132771936-a99bdfec-efd3-44b4-adc7-8ddf510c87a4.png" />
<br/>
<br/>
rij = ‖p −pi‖−‖p −pj ‖ 
<br/>
ri = ‖p −pi‖

<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>





## DOP: The Dilution of Precision
- DOP provides a gain factor, which is a dimension-less number – it says how much the position error is amplified at a given point of space by the anchors’ geometry. To make it clear, the distance between anchors does not affect DOP at all. It is just their pure geometry that has an impact.
- The idea of Geometric DOP is to state how errors in the measurement will affect the final state estimation.

<img align="right" width="300" src="https://user-images.githubusercontent.com/46463022/133940819-99f276b5-b94d-41f5-b350-52669dc159ff.png">

- DOP can be expressed as a number of separate measurements:
    - HDOP – horizontal dilution of precision
    - VDOP – vertical dilution of precision
    - PDOP – position (3D) dilution of precision
    - TDOP – time dilution of precision
    - GDOP – geometric dilution of precision

<br/>
<br/>
<br/>
<br/>

<p align="center">
   <img src=https://user-images.githubusercontent.com/46463022/133940483-b96725a7-ef5d-4c62-86e0-92411ab89644.png>
</p>

DOP Rating :
   - 1 Ideal 
   - 2 – 3 Excellent 
   - 4 – 6 Good 
   - 7 – 8 Moderate 
   - 9 – 20 Fair 
   - 21 – 50 Poor

***Reminder:***  
***(Dev. Score, centered Matrix) Xc= X - X̄***  
***Cov_Matrix: Xc'Xc/n***


## K-d tree
*  k-dimensional tree) is a space-partitioning data structure for organizing points in a k-dimensional space.
*  applications: searches involving a multidimensional search key (e.g. range searches and nearest neighbor searches)



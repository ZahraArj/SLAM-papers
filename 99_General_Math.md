
   <!---
Started to write on Sep 9 2021
Zahra
-->

## [Lie Algebras](https://www.math.uni-hamburg.de/home/wockel/teaching/data/cohomology_of_lie_algebras_imani.pdf)

## [Exponential map](https://math.stackexchange.com/questions/999515/meaning-of-exponential-map)
   The idea of an exponential is the continuous compounding of small actions.

## [SE(3)](https://rock-learning.github.io/pytransform3d/transformations.html)
   The group of all transformations in the 3D Cartesian space is SE(3) (SE: Special Euclidean group). Transformations consist of a rotation and a translation. Those can be represented in different ways just like rotations can be expressed in different ways.  
   All transformation matrices form the special Euclidean group SE(3).  
 <p align="center">
   <img src="https://user-images.githubusercontent.com/46463022/132751832-1101fca9-34db-48e9-970d-e0b155892fc1.png" width="500">
 </p>
 
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
<img align="right" width="400" src="https://user-images.githubusercontent.com/46463022/132772005-229411ec-96fa-449d-b691-c6df1db1b59a.png" />   
<img align="left" width="400" src="https://user-images.githubusercontent.com/46463022/132771936-a99bdfec-efd3-44b4-adc7-8ddf510c87a4.png" />   

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

***Reminder: (Dev. Score, centered Matrix) Xc= X - X̄***
***Cov_Matrix: Xc'Xc/n***




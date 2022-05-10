<!---
Started to write on May 5 2022
Zahra
-->
Link: [A Benchmark for the Evaluation of RGB-D SLAM Systems](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=6385773)
## Relative pose error (RPE)
The relative pose error measures the local accuracy of the trajectory over a fixed time interval ∆. 
Therefore, the relative pose error corresponds to the drift of the trajectory.

poses from the estimated trajectory P1, . . . , Pn ∈ SE(3)  
and from the ground truth trajectory Q1, . . . , Qn ∈ SE(3)

![a](https://user-images.githubusercontent.com/46463022/167691155-17122ce1-5ea1-4866-8808-f949885e6673.PNG)  
![dd](https://user-images.githubusercontent.com/46463022/167691186-312da917-608a-4378-adc7-4aed9c32bd1f.PNG)  

![image](https://user-images.githubusercontent.com/46463022/167692812-2b6b5f5c-13fa-47f9-8e36-adc52d8ae587.png)  
![image](https://user-images.githubusercontent.com/46463022/167692851-9205627a-83c4-48ec-81be-56908e2919cc.png)  


## Absolute trajectory error (ATE)
Comparing the absolute distances between the estimated and the ground truth trajectory.  
![image](https://user-images.githubusercontent.com/46463022/167691960-596e1db0-4f01-4715-99be-b701a0684dfe.png)  
![image](https://user-images.githubusercontent.com/46463022/167692013-cbfb05c3-7325-4a67-9d67-3e5023ce7493.png)  


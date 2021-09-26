# References



<!---
Started to write on Sep 1 2021
Zahra
-->

## BASICS
1. ***LOAMS***  (LiDAR odometry & mapping)
    1. [LOAM 2014: Lidar Odometry and Mapping in Real-time](https://www.ri.cmu.edu/pub_files/2014/7/Ji_LidarMapping_RSS2014_v8.pdf)
    2. [LOAM 2016: Low-drift and real-time lidar odometry and mapping](https://link.springer.com/content/pdf/10.1007/s10514-016-9548-2.pdf) 
    3. [V-LOAM 2015: Visual-lidar Odometry and Mapping: Low-drift, Robust, and Fast](https://frc.ri.cmu.edu/~zhangji/publications/ICRA_2015.pdf) 
    4. [LeGO-LOAM 2018: Lightweight and Ground-Optimized Lidar Odometry and Mapping on Variable Terrain](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8594299)  
       - Simplified LOAM (for ground vehicle) + Loop Closing  
2. ***LIO***  (lidar- IMU odometry)
    1. [LIO 2019: Tightly Coupled 3D Lidar Inertial Odometry and Mapping](https://arxiv.org/pdf/1904.06993.pdf)
    2. [LIO-SAM 2020: Tightly-coupled Lidar Inertial Odometry via Smoothing and Mapping](https://arxiv.org/pdf/2007.00258.pdf)
        - LeGO-LOAM + IMU + GPS
    3. [LVI-SAM 2021: Tightly-coupled Lidar-Visual-Inertial Odometry via Smoothing and Mapping](https://arxiv.org/pdf/2104.10831.pdf)
        - LIO-SAM + Vision
    4. [DeepLIO 2021: Deep LIDAR Inertial Sensor Fusion for Odometry Estimation ](https://www.researchgate.net/publication/352498082_DEEPLIO_DEEP_LIDAR_INERTIAL_SENSOR_FUSION_FOR_ODOMETRY_ESTIMATION)

<br/>
<br/>

## ICRA 2021
1. **[Unsupervised Learning of Lidar Features for Use in a Probabilistic Trajectory Estimator](https://arxiv.org/pdf/2102.11261.pdf)**
    - [ICRA 2021 Best Student Paper Award.](https://www.youtube.com/watch?v=RU5ZMXdDewQ)
    - [Tim Barfoot - Autonomous Space Robotics Lab, UoT](http://asrl.utias.utoronto.ca/~tdb/)  
    - **Unsupervised Learning of Lidar Features**  
    <p float="left">
      <img src="https://user-images.githubusercontent.com/46463022/131919839-99f72eeb-a77f-4138-8b57-2af758603d30.png" height="150">
      <img src="https://user-images.githubusercontent.com/46463022/131920410-d063251f-64e3-4340-97ab-08562b5d987e.png" height="200">
    </p>
    <br/>
    
2. **[Radar Odometry Combining Probabilistic Estimation and Unsupervised Feature Learning](https://arxiv.org/pdf/2105.14152.pdf)**
    - Same lab  
    - Not ICRA, **arxiv**   
      <img src="https://user-images.githubusercontent.com/46463022/131921132-d3be8026-e3f9-4b40-b91a-2eb369eeb808.png" width="700">
      <br/>
      
3. **[Self-supervised Learning of LiDAR Odometry for Robotic Applications](https://arxiv.org/pdf/2011.05418.pdf)**  
    - Robotic Systems Lab, **ETH Zurich**  
    - Geometric Loss  
    <img src="https://user-images.githubusercontent.com/46463022/131921721-4e8bedf3-b61f-43c3-a330-5e667cd5361f.png" width="700">
    <br/>
4. **[Interval-Based Visual-LiDAR Sensor Fusion](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9349119)**  
5. **[Dynamic  Object  Aware  LiDAR  SLAM  based  on  Automatic  Generationof  Training  Data](https://arxiv.org/pdf/2104.03657.pdf)**
6. **[Self-Supervised Learning of Lidar Segmentation for Autonomous Indoor Navigation](https://arxiv.org/pdf/2012.05897.pdf)**

<br/>
<br/>


## UWB UoT, Prof. Angela Schoellig, [Dynamic Systems Lab](https://www.dynsyslab.org/vision-news/)

### [2021: Learning-based Bias Correction for Time Difference of Arrival Ultra-wideband Localization of Resource-constrained Mobile Robots ](https://arxiv.org/abs/2103.01885)  
![2021](https://user-images.githubusercontent.com/46463022/131751263-a1e44428-31bc-495f-8f5f-13f93756a9cd.png)

#### Theory
- Due to the model nonlinearity, we use an M-estimation based extended Kalman filter (EKF) to estimate the states. Replacing the quadratic cost function in a conventional Kalman filter with a robust cost function ρ(·)—e.g. Geman- McClure (G-M), Huber or Cauchy.
    - The M estimators: try to reduce the effect of outliers by replacing the squared residuals r^2 by another function of the residuals, yielding: minⵉρ(r)
    - The standard least squares metho d tries to minimize minⵉ(r^2) which is unstable if there are outliers present in the data.
![Screenshot from 2021-09-20 16-08-08](https://user-images.githubusercontent.com/46463022/134068445-f411f5bf-3cfc-4d33-919e-7ac2c8e9eb06.png)


### [2020: Learning-based Bias Correction for Ultra-wideband Localizationof Resource-constrained Mobile Robots ](https://arxiv.org/abs/2003.09371)  
![2020](https://user-images.githubusercontent.com/46463022/131751671-faa3a935-83a7-49ce-b38e-5eedd06da3ba.png)   
#### Cited:
- Benchmark Dataset of Ultra-Wideband Radio Based UAV Positioning
- [Automated Tuning of End-to-end Neural Flight Controllers for Autonomous Nano-drones](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9458550)
- [Fully Onboard AI-powered Human-Drone Pose Estimation on Ultra-low Power Autonomous Flying Nano-UAVs](https://arxiv.org/pdf/2103.10873.pdf)
- [Heading Estimation Using Ultra-wideband Received Signal Strength and Gaussian Processes](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9508865)
- [Sensor Information Sharing Using a Producer-Consumer Algorithm on Small Vehicles ](https://www.mdpi.com/1424-8220/21/9/3022/htm)
#### Theory
##### Two-step measurement correction:
1. **Statistical outlier rejection**
    * Using robot’s dynamics to filter inconsistent UWB range measurements: the maximum distance max a quadcopter can cover during time ∆t: dmax = ‖v∆t + 1
2 amax∆t2‖
    * statistical hypothesis: S = GPG + R (EKF: use the χ2 hypothesis test to determine whether a measurement innovation is likely coming from the distribution)

2. **NN Bias compensation: spatially varying bias of TWR and TDoA measurements**
    * Exclusively trained our NN with measurement whose actual bias less within a threshold of 0.7m
##### Notes
- Mitigation of UWB TWR measurement errors: (most of them leverage **probabilistic methods**)
    - Systematic biases 
    - NLOS
    - Multipath propagation
- Since multi-path and NLOS propagation effects depend on a particular indoor environment, we only use the NN to explicitly model the pose-dependent bias. 
 
<br/>
<br/>
      
### Visual Localization UoT, Prof. Jonathan Kelly, [STARS Lab](https://starslab.ca/)

- [2020: Self-Supervised Deep Pose Corrections for Robust Visual Odometry](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9197562)
- [2018: VDPC-Net: Deep Pose Correction for Visual Localization](https://arxiv.org/pdf/1709.03128.pdf) 

| 2018      | 2020 |
| ----------- | ----------- |
| ![](https://user-images.githubusercontent.com/46463022/132727336-fb115aa9-dbc7-4e9f-9b4a-c3f684a1a0f6.png)| ![](https://user-images.githubusercontent.com/46463022/134822075-a9a7bdb6-5daa-436c-89f5-3a6c6c9a70a5.png)|

2020
---
They replace the supervised loss of DPC-Net with a photometric reconstruction loss that does not require any external ground truth pose information.
**Note: Self supervised vs unsupervised: There is a supervised training signal in these methods.**

2018
---

#### Theory:
* In contrast to other methods that completely replace a classical visual estimator with a deep network, we propose an approach that uses a convolutional neural network to learn difficult-to-model **corrections to the estimator** from ground-truth training data. 
* A novel loss function for learning **SE(3) corrections based on a matrix Lie groups** approach, with a natural formulation for balancing translation and rotation errors
* They **use this loss to train** a Deep Pose Correction network (DPC-Net) that predicts corrections for a particular estimator, sensor and environment.
* Others for loss function : based on SE(3) geodesic distance.
* Their loss naturally balances translation and rotation error without requiring a hand-tuned scalar hyper-paramete

Tcorr corrects a classical VO estimate:
![Screenshot from 2021-09-26 16-37-38](https://user-images.githubusercontent.com/46463022/134823411-4c71f420-e14d-4ea5-8f6e-966b870580ca.png)
To **parameterize this correction**:
![Screenshot from 2021-09-26 16-37-46](https://user-images.githubusercontent.com/46463022/134823429-f72f0e0d-8a22-483f-a16d-4b33bc3e0613.png)



<br/>
<br/>

#### Cited
1- [Learning Wheel Odometry and IMU Errors for Localization](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8794237)  
2- [A Smooth Representation of Belief over SO(3) for Deep Rotation Learning with Uncertainty](https://arxiv.org/pdf/2006.01031.pdf)  
3- [The Complex-Step Derivative Approximation on Matrix Lie Groups](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8957301)  
4- [Probabilistic Regression of Rotations using Quaternion Averaging and a Deep Multi-Headed Network](https://arxiv.org/pdf/1904.03182.pdf)  
5- [mproving Learning-based Ego-motion Estimation with Homomorphism-based Losses and Drift Correction](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8968515)  
5- [A Stacked LSTM-Based Approach for Reducing Semantic Pose Estimation ErrorRana](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9235399)


### Comparision between different methods
- [What s in My LiDAR Odometry Toolbox?](https://arxiv.org/abs/2103.09708)  
![comparision](https://user-images.githubusercontent.com/46463022/131752670-51148481-b147-42be-8f3c-5984f033c786.png)

<br/>
<br/>


- DeepLIO

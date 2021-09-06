# References



<!---
Started to write on Sep 1 2021
Zahra
-->

### BASICS
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

### ICRA 2021
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
    
### UWB UoT, Prof. Angela Schoellig, [Dynamic Systems Lab](https://www.dynsyslab.org/vision-news/)

- [2020: Learning-based Bias Correction for Ultra-wideband Localizationof Resource-constrained Mobile Robots ](https://arxiv.org/abs/2003.09371)  
![2020](https://user-images.githubusercontent.com/46463022/131751671-faa3a935-83a7-49ce-b38e-5eedd06da3ba.png) 
        - cited:
            - Benchmark Dataset of Ultra-Wideband Radio Based UAV Positioning
            - [Automated Tuning of End-to-end Neural Flight Controllers for Autonomous Nano-drones](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9458550)
            - [Fully Onboard AI-powered Human-Drone Pose Estimation on Ultra-low Power Autonomous Flying Nano-UAVs](https://arxiv.org/pdf/2103.10873.pdf)
            - [Heading Estimation Using Ultra-wideband Received Signal Strength and Gaussian Processes](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9508865)
            - [Sensor Information Sharing Using a Producer-Consumer Algorithm on Small Vehicles ](https://www.mdpi.com/1424-8220/21/9/3022/htm)
    
- [2021: Learning-based Bias Correction for Time Difference of Arrival Ultra-wideband Localization of Resource-constrained Mobile Robots ](https://arxiv.org/abs/2103.01885)  
![2021](https://user-images.githubusercontent.com/46463022/131751263-a1e44428-31bc-495f-8f5f-13f93756a9cd.png)

<br/>
<br/>


### Comparision between different methods
- [What s in My LiDAR Odometry Toolbox?](https://arxiv.org/abs/2103.09708)  
![comparision](https://user-images.githubusercontent.com/46463022/131752670-51148481-b147-42be-8f3c-5984f033c786.png)

<br/>
<br/>


- DeepLIO


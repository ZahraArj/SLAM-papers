## [Laser-visual-inertial Odometry and Mapping with High Robustness and Low Drift](file:///tmp/mozilla_zara0/JFR2018.pdf)

* Different from traditional methods that use a Kalman filter or factor‐graph optimization.
* Sequential, multilayer processing pipeline, solving for motion from coarse to fine.


## LVI-SAM: Tightly-coupled Lidar-Visual-Inertial Odometry via Smoothing and Mapping
![image](https://user-images.githubusercontent.com/46463022/146050754-5bde44aa-4c0a-4cca-a6fc-2c9f6dfa12b9.png)

![image](https://user-images.githubusercontent.com/46463022/146050785-1deadf7e-b34e-40d7-9c80-a6ed4308d659.png)

### 1. Visual-Inertial System

system state : x = [ R, p, v, b] . (SO(3): the rotation matrix, position, speed, [ ba, bw ])


1. Initialization: estimated system state x and IMU bias b from the LIS
* Because depth is directly observable from a lidar, we first initialize the LIS and obtain x and b. Then we interpolate and associate them to each image keyframe based on the image timestamp. Note that the IMU bias is assumed to be constant between two image keyframes. Finally, the estimated x and b from the LIS are used as the initial guess for VIS initialization, which significantly improves initialization speed and robustness.
* when the sensor travels at a small or constant velocity. This is due to the fact that metric scale is not observable when acceleration excitation is not large enough. The IMU parameters include a slowly varying bias and white noise, which effect both the raw acceleration and angular velocity measurements. 

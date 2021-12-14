## [Laser-visual-inertial Odometry and Mapping with High Robustness and Low Drift](file:///tmp/mozilla_zara0/JFR2018.pdf)

* Different from traditional methods that use a Kalman filter or factor‐graph optimization.
* Sequential, multilayer processing pipeline, solving for motion from coarse to fine.


## LVI-SAM: Tightly-coupled Lidar-Visual-Inertial Odometry via Smoothing and Mapping
![image](https://user-images.githubusercontent.com/46463022/146050754-5bde44aa-4c0a-4cca-a6fc-2c9f6dfa12b9.png)

![image](https://user-images.githubusercontent.com/46463022/146050785-1deadf7e-b34e-40d7-9c80-a6ed4308d659.png)

### 1. Visual-Inertial System

system state : x = [ R, p, v, b] . (SO(3): the rotation matrix, position, speed, [ ba, bw ])


#### 1. Initialization: estimated system state x and IMU bias b from the LIS
* Because depth is directly observable from a lidar, we first initialize the LIS and obtain x and b. Then we interpolate and associate them to each image keyframe based on the image timestamp. Note that the IMU bias is assumed to be constant between two image keyframes. Finally, the estimated x and b from the LIS are used as the initial guess for VIS initialization, which significantly improves initialization speed and robustness.
* when the sensor travels at a small or constant velocity. This is due to the fact that metric scale is not observable when acceleration excitation is not large enough. The IMU parameters include a slowly varying bias and white noise, which effect both the raw acceleration and angular velocity measurements. 

#### 2. Feature depth association
* stack multiple lidar frames to obtain a dense depth map.
* project visual features and lidar depth points on a unit sphere that is centered at the camera.
* Depth points are then downsampled and stored using their polar coordinates for a constant density on the sphere.
* find the nearest three depth points on the sphere for a visual feature by searching a two-dimensional K-D tree using the polar coordinates of the visual feature. 
  ![image](https://user-images.githubusercontent.com/46463022/146060560-75a9fc84-4f3a-4ff3-9bd1-28389208e36f.png)
* validate the associated feature depth: check- ing the distance among the three nearest depth points.(tacking lidar frames from different timestamps may result in depth ambiguity from different objects. )
  ![image](https://user-images.githubusercontent.com/46463022/146068182-26070df2-4bce-4b75-9c26-675eac824e81.png)
#### 3. Failure detection


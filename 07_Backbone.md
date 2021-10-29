
# SLAM Backbone

Conventional navigation systems are able to provide either constant-time updates or the ability to incorporate loop closures, but not both. 

## **Constant-time updates:**
### 1. EKF-based methods:
  *  Maintain constant-time updates by marginalizing out all past variables   
     *  Variations on the EKF, such as augmented state filters or fixed-lag smoothers, maintain only a subset of the past states to improve estimation accuracy
  *  Fuse the local estimation into the global frame gradually  
  * **Disadvantages**  
    *  An accurate initial guess about the transformation between different frames is required to guarantee convergence.
    *  Sensitive to time synchronization: Any late-coming measurements will cause trouble since states cannot be propagated back in filter procedure.
### 2. Particle Filter (Sequential Monte Carlo)

## **Loop Closure:**
* Estimate the value of all past states within the optimization  
* **Disadvantages**  
  * Computational complexity
  * Even while leveraging the inherent sparsity of the problem and utilizing the latest algorithms for performing incremental inference, constant-time updates in the presence of loop closures cannot be achieved.

### 3. Pose Graph
### 4. Bundle Adjustment

Providing both: **Parallelization**
 * **Basic idea:** have a low-latency process update the current state at a high rate while a slower background process performs ful.
 * **Challenge:** the information exchange or synchronization of the two processes

https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7181037/
## Visual SLAM
1. Feature Based SLAM
2. Direct SLAM
3. RGB-D SLAM  
![Screenshot from 2021-10-26 19-07-18](https://user-images.githubusercontent.com/46463022/138973630-2c726c52-d7d4-409b-8ee7-ad5172c59d34.png)

## LiDAR Based SLAM
1. Scan-Matching and Graph Optimization
   * Occupancy Map and Particle Filter
   * Loop Closure Refinement Step  
![Screenshot from 2021-10-26 19-11-32](https://user-images.githubusercontent.com/46463022/138973920-85c57386-6db3-40d2-9116-89dd0c24b1fb.png)

## LiDAR-Camera Fusion
1. The Mandatory Calibration Step
2. Fusion:
    *  EKF Hybridized SLAM
    *  Improved Visual SLAM
    *  Improved LiDAR SLAM
    *  Concurrent LiDAR-Visual SLAM


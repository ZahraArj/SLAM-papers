# MMS Systems


## 1- [SLAM integrated mobile mapping system in complex urban environments](https://www.sciencedirect.com/science/article/pii/S0924271620301386)
* They establish a SLAM-integrated MMS with the capability of efficient, consistent and robust mapping in complex en- vironments where GNSS signal is intermittently lost.
* Fisrt: derived the probabilistic model for SLAM-integrated MMS, which abstractly proved the advances of adding the feedback from the mapping module to the localization module.
* Second: Describe details of the hierarchical factor graph optimization structure, which is the core of the proposed method.
  * Essential factor graph: dumps all redundant factors to keep the global graph concise and tight.
  * iSAM (incremental smoothing and mapping) algorithm is employed off-line to efficiently solve the global optimization.
* Point cloud registration is performed on GPU using surfel-based approach to speed up.
### Traditional MMS
1. combining INS and GNSS
2. +Lidar
3. GNSS-denied area: 
   * automatic registration of point cloud map from multiple passes: requires data from multiple passes of the same scene and require manual adjustment.
   * Hussnain et al. (2018) extracted the known landmarks in the environment as control points. (against SLAM idea)

### Maximum a posteriori estimation  
* multi-source data fusion technique 
* From the perspective of probability, the estimation of robot poses can be transformed as maximizing the conditional distribution of robot pose, given the noise model of all on- board sensors.
  * (1) filtering methods, e.g. Extended Kalman Filter (EKF), and Particle Filter (PF), 
  * (2) and smoothing methods.
    * Full smoothing: optimizes entire history of states
    * Fixed-lag smoothing: optimizes states falling within a given time window 
      * compromise of filter approaches and full smoothing approaches. accuracy is higher than filter approaches because they re-linearize past measurements.)
      * The disadvantage is that the marginalization of old tates destructs the sparsity of hessian matrix, which decreases the effciency of optimization.
    * iSAM (Incremental Smoothing and Mappng): STOA. Opimizes a small subset of variables dentified as affected nodes by the new measurement
### LiDAR-based SLAM
Failure: structureless environment or under rapid rotation
* 1. classical point-based **ICP** registration
  * Costs too much on closest points searching
  * May get stuck into the local optimum, when a bad initial is provided
 * 2. **LOAM**
   *  divided SLAM prblem into the odometry and the mapping thread (performed feature-based scan-to-scan registration on odometry at high frequency, while preformed feature-based scan-to-map registration on the parallel Mapping thread at lower frequency)
   *  lacks an optimization back-end, which makes error accumulation
 * 3. **Lego_Loam**: Aded an optimization back-end for LOAM\
 * 4. **SuMa(Surfel Mapping):** surfel-based SLAM
   * A global surfel-based map was constructed and maintained. 
   * The surfel-based ICP algorithm is a variation of classical ICP.
   * It project points as the depth image, so that correspondences can be directly found by indexing the same pixel in a pair of successive depth images, which avoids the costly searching and increase the convergency of the estimation iteration.
   * he changes of poses were estimated by exploiting the projective data associations between current laser scan and a rendered model view from the global point cloud map.
 * 5. **SuMa++:** SuMa + RangeNet++
   * Improve the registration accuracy in dynamic environment: Remove the moving objects in the point cloud and build a semantic map.

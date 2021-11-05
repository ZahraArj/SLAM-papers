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
 ### SLAM + MMS  (during GNSS outages)
 * Indoortechniques: indoor environment is well-structured, i.e. indoor free space is flat and full of lines and surfaces: Good for 2D SLAM solutions
   * Gmapping
   * Cartographer
 * Totally GNSS denied environment
 * **GNSS is sporadic:**  
   GNSS signals are unavailable: Blocked or effected by multi-path effect  
   They set the time periods of GNSS-denied as 5s, 10s, 15s, 20s, 25s, 30s, 40s, 50s and 60s  
   
   *  1- [Pseudo-GNSS/INS system](https://ieeexplore.ieee.org/document/8373382)  
      These sensors provide the data stream for map construction.  
      The key of this is transforming the pose estimation by SLAM to Pseudo-GNSS signals. To improve the efficiency of the mapping optimization  
      EKF
      |  GNSS/INS-based MMS             |  proposed Pseudo-GNSS/INS framework |
      :-------------------------:|:-------------------------:
      ![Screenshot from 2021-11-03 16-02-31](https://user-images.githubusercontent.com/46463022/140184443-3b8f3481-2f95-4d69-a818-c4259cef2dc6.png)|![Screenshot from 2021-11-03 16-02-42](https://user-images.githubusercontent.com/46463022/140184454-d1be3b14-8c4e-4354-9322-77d27b547681.png)
   *  2- [Image-assisted gnss/ins navigation for uav-based mobile mapping systems during gnss outages.](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8373409)  
       Hierarchical filter along with smoothers  
       1- The first stage is a tightly coupled Kalman Filter (KF) followed by a smoother using GNSS/INS measurements as inputs.  
       2- The second stage is a loosely coupled KF utilizing the output from the first stage and a vision-based trajectory to aid trajectory refinement during GNSS outages.
       |  idea             |  detailed  |
       :-------------------------:|:-------------------------:
       ![Screenshot from 2021-11-03 16-37-26](https://user-images.githubusercontent.com/46463022/140188949-aaae8e23-79b2-4b51-a113-68c2f4cac4c7.png)|![Screenshot from 2021-11-03 16-39-39](https://user-images.githubusercontent.com/46463022/140189224-7c159643-ddfc-435b-94a0-990b828e97be.png)
### System overview   
1- Green blocks: raw data  
   * IMU/GNSS > EKF 
   * GNSS Unavailable: IMU only
   * Lidar: Relative transformation
2- Pose Graph(first)
   * IMU preintegrated factors (GNSS signalk locked)
     * Or odometry factors: GNSS/IMU filter
   * scan-to-map registration factors (surfel-based:SuMa)
   * small loop factors (surfel-based:SuMa)
3- when GNSS signal is lost, construction time of a submap span a long period of time:  surfel-based approach may fail.
   * change to use point-based registration
   
   ![Screenshot from 2021-11-04 13-28-22](https://user-images.githubusercontent.com/46463022/140389526-c8b06632-ff8d-4bdf-a092-7f84eb2225c7.png)
### Hierarchical optimization structure
 | Local refinement | Global refinement |
 :-------------------------:|:-------------------------:
 ![Screenshot from 2021-11-04 16-03-52](https://user-images.githubusercontent.com/46463022/140411779-d6c1dbf4-c060-4eb6-9a28-711bbcc5d535.png)|![Screenshot from 2021-11-04 16-04-01](https://user-images.githubusercontent.com/46463022/140411795-ee84bece-1065-4a4c-b3a5-7c4ad9a0a28c.png)
 Scan-to-map registration factor|Map-to-map registration factor
 
 ### Cited
 
 ## 1- Continuous-Time Laser Frames Associating and Mapping via Multilayer Optimization  
 *  No GNSS/INS
 *  Normal distributions transform (NDT) and ICP  
 *  Continuous-time laser frames associating and mapping framework  
    * 1- Intraframe point cloud segmentation (RANSAC)
    * 2- Interframe point cloud association (NDT)  
         match the consecutive frames with the ground points and effective non-ground points
    * 3- Submap matching (ICP)  
         the first frame of the submap is used as a key frame
    * 4- Closed loop detection (NDT)
    * 5- Graph optimization:
    ![Screenshot from 2021-11-04 17-45-38](https://user-images.githubusercontent.com/46463022/140424670-e4938714-3fad-4505-b7ba-04f014b2421e.png)
 * Three-layer point cloud association technique.
    ![Screenshot from 2021-11-04 17-55-11](https://user-images.githubusercontent.com/46463022/140425701-038f143f-ac75-485a-9d94-4ea97809fc00.png)

 | :full_moon: Note: (LOAM):Uses features to align consecutive frames   |
| --- |
[NDT:Normal Distributions Transform](https://journals.sagepub.com/doi/10.1177/1729881419841532) :interframe association of sparse point clouds (match the point clouds with a global map)
The interframe point cloud association method: |
1- ICP: easy to fall into the local optimum|
2- fast point feature histogram (FPFH): expensive computational costs|
3- Super-4PCS: global search with (RANSAC), ostly in computation but has higher association accuracy|
4-  normal distributions transform (NDT): fastest and relatively reliable method

## 2- MULLS: Versatile LiDAR SLAM via Multi-metric Linear Least Square
* With low drift 
* Real-time performance
* Rank 13th KITTI benchmark  
### Overall workﬂow of MULLS-SLAM
  ![image](https://user-images.githubusercontent.com/46463022/140562280-179f9bd5-64f9-48c4-8d0d-7aba135b828a.png)

### Front-end:
  * Roughly classified feature points
  * Multi-metric Linear Square (MULLS) ICP
  * Local map updating
### Back-end: 
  * Submap-based loop closure
  * TEASER-based global registration 
  * Inter & inner submap PGO
### Point Cloud Registration (scan matching):
  * Local: Requires good initial guess 
  * Global: Coarsely align them 
  * Deep Learning
    * First learn to embed points 
    * Learn to match keypoints 
    * Optimization
      PointNet, DGCNN, PointNetLK, DCP,…
### Local Matching:
  * ICP (Iterative closest point)
  * Sparse point-based:   
    * LO, LOAM (The edge and planar points)
    * LeGO-LOAM (Conduct ground segmentation )
  * Dense projective normal ICP: 
    * Suma
			 * SuMa++ (Semantic masks)
  * Limitations:
    * Requires an initial guess
    * Lose 3D information due to the operation based on range image or scan-line
### Pose Graph Optimization
![image](https://user-images.githubusercontent.com/46463022/140562371-80c01399-fd37-482d-aa4b-9ddd497c3d9b.png)


 | Pipeline of geometric feature points extraction and encoding | Pipeline of the multi-metric linear least square ICP |
 :-------------------------:|:-------------------------:
 ![image](https://user-images.githubusercontent.com/46463022/140562735-c24fa299-8d6f-45e5-8696-c54d8a59dbac.png)| ![image](https://user-images.githubusercontent.com/46463022/140563643-c75342bb-561d-42bf-a9f0-84333372cd63.png)|

 








 






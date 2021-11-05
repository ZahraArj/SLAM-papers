

# ***LOAMS***  (LiDAR odometry & mapping)
1. [LOAM 2014: Lidar Odometry and Mapping in Real-time](https://www.ri.cmu.edu/pub_files/2014/7/Ji_LidarMapping_RSS2014_v8.pdf)
2. [LOAM 2016: Low-drift and real-time lidar odometry and mapping](https://link.springer.com/content/pdf/10.1007/s10514-016-9548-2.pdf) 
3. [V-LOAM 2015: Visual-lidar Odometry and Mapping: Low-drift, Robust, and Fast](https://frc.ri.cmu.edu/~zhangji/publications/ICRA_2015.pdf) 
4. [LeGO-LOAM 2018: Lightweight and Ground-Optimized Lidar Odometry and Mapping on Variable Terrain](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8594299)  
    - Simplified LOAM (for ground vehicle) + Loop Closing  
# LOAM

## 1. Feature Point Extraction
- Dividing each scan it into four identical sub-regions. 
- A sub-region is a subset of points of each scan. 
- The LOAM feature extractor is responsible for classifying each point of all sub-regions as smooth (flat) or non-smooth (sharp) according to a threshold. 
- This threshold is represented by CLOAM and it is defined as:  

![Screenshot from 2021-10-15 12-09-25](https://user-images.githubusercontent.com/46463022/137519145-83290d06-8103-4e95-94b6-8195065d7c35.png)

- R is the set of points from a sub-region of a scan (R⊂Pk). 
- p(i,k) and p(j,k) represent the ith and jth point vectors of the sweep k of R. 
- || ||represents the L2 norm.



| :full_moon: Note: Convolution is a mathematical way of combining two signals to form a third signal. This means that the filter convolves around the input volume by shifting n unit at a time. Equal to product of the Fourier Transforms of the functions |
| --- |


* The points in a scan are sorted based on the c values (maximum c’s: edge points, minimum c’s: planar points.) (larger or smaller than a threshold,)
* To evenly distribute the feature points within the environment:  separate a scan into four identical subregions. (Each subregion: maximally 2 edge points and 4 planar points. )
* the number of selected points does not exceed the maximum.
* selecting feature points
* unreliable: 
    * avoid points whose surrounded points are selected
    * points on local planar surfaces that are roughly parallel to the laser beams (point B in Fig. 4(a))
    * points that are on boundary of occluded regions
    
![](https://user-images.githubusercontent.com/46463022/138727497-5e05cb8e-45b3-40b8-bd53-d042a0657e46.PNG)

# 2. Finding Feature Point Correspondence

Inputs:  
* ~Pk: Pk that reprojected to time stamp tk+1   
* Pk+1:  
    * Ek+1 edge points 
    * Hk+1 planar points  
    
Finding correspondences between the two lidar clouds:    
* The lidar odometry recursively estimates the 6-DOF motion during the sweep, and gradually includes more points as Pk+1 increases. 
* At each iteration, Ek+1 and Hk+1 are reprojected to the beginning of the sweep using the currently estimated transform. Let  ̃Ek+1 and  ̃Hk+1 be the reprojected point sets. For each point in  ̃Ek+1 and  ̃Hk+1, we are going to find the closest neighbor point in  ̄Pk. Here,  ̄Pk is stored in a 3D KD-tree [24] for fast index.

# Lego LOAM
* real-time
* Velodyne
* Apply point cloud segmentation to filter out noise
  * Noise
  * Ground: for planar features
  * else: for edge features
  ![image](https://user-images.githubusercontent.com/46463022/140568276-76c105cb-c0e2-4ece-96e5-6f20bbd9687c.png)

* The feature extraction process is similar to LOAM
  * instead of extracting features from raw point clouds, they extract features from ground points and segmented points.
* 

![image](https://user-images.githubusercontent.com/46463022/140566673-ecd69c8b-3b85-4020-9312-3b10cbaa7d47.png)


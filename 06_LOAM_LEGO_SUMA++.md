

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


https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8023504
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

# [Lego LOAM 2018](https://ieeexplore.ieee.org/document/8594299)
* real-time
* Velodyne
* The feature extraction process is similar to LOAM
  * instead of extracting features from raw point clouds, they extract features from ground points and segmented points. 
## Point cloud segmentation
  * Noise
  * Ground: for planar features
  * else: for edge features  (and planar)  
    ![image](https://user-images.githubusercontent.com/46463022/140568276-76c105cb-c0e2-4ece-96e5-6f20bbd9687c.png)

## System Overview 
![image](https://user-images.githubusercontent.com/46463022/140566673-ecd69c8b-3b85-4020-9312-3b10cbaa7d47.png)

## Result
Paths produced by LOAM and LeGO-LOAM across 10 trials, and 2 computers, with the **experiment 3** dataset.
![image](https://user-images.githubusercontent.com/46463022/140570608-3d7e4fb7-d09a-4a44-8e2a-0169b7ef9625.png)

![image](https://user-images.githubusercontent.com/46463022/140571198-d4688e56-984a-4917-8ace-cdd2d4fc547e.png)

# [Suma 2018](http://www.roboticsproceedings.org/rss14/p16.pdf)
![image](https://user-images.githubusercontent.com/46463022/140579469-d41fb5e3-b22a-4916-a374-7e3b447ed019.png)

* 1- Projection function Π R3→R2: 
  * Generate a vertex map (spherical projection) VD : R2 → R3 mapping a two-dimensional image coordinate (u,v)T ∈ R2 to a point (x,y,z)T ∈ R3. 
  * Generate a corresponding normal map ND : R2 →R3 exploiting the vertex map VD  
    ![image](https://user-images.githubusercontent.com/46463022/140581462-3b4533ba-5956-4396-8599-5fbe39f73271.png)
* 3- Odometry (ICP)

  
* A dense mapping approach called Surfel-based Mappin  
* Surfel -based:
  * Allows us to represent even large-scale environments and maintain dense, , detailed geometric information of the point clouds at the same time.
  * Relatively fast to render
  * A surfel map M is an unordered set of surfels s, where each surfel is defined by a position vs ∈ R3, a normal ns ∈ R3, a radius rs ∈ R.
    ![image](https://user-images.githubusercontent.com/46463022/140579212-70a2b214-d8f7-4480-9993-fade065f1c7d.png)
    
# [Suma++ 2019](https://www.ipb.uni-bonn.de/wp-content/papercite-data/pdf/chen2019iros.pdf)
![image](https://user-images.githubusercontent.com/46463022/140583249-522ae254-0449-43a3-9d87-15f4ecae1026.png)
* Real-time
* Integrating semantic information to facilitate the mapping process.
* The semantic information is efficiently extracted by a fully convolutional neural network and rendered on a spherical projection of the laser range data.
* This semantic map enables us to reliably filter moving objects, but also improve the projective scan matching via semantic constraints.
* It exploits the labels provided by the semantic segmentation to handle moving objects. More specifically, It filters dynamics by checking semantic consistency between the new observation and the world model, when we update the map. If the labels are inconsistent we assume those surfels belong to an object that moved between the scans. Therefore, we add a penalty term to the computation of the stability term in the recursive Bayes filter. After several observations, we can remove the unstable surfels. In this way, we achieve a detection of dynamics and finally a removal.
* Semantic information: 
  * Removing moving objects: inconsistency between current scan and the map
  * Fll-in eroded labels with neighboring labels to get a more consistent result
  * Creating semantic map
* Suma:
  * **Suma
  * **Suma_no_movable:** naive approach of removing all movable classes (vehicles, persons,...) 
  * **Suma++**

    

#[3D Feature Points Detection on Sparse and Non-uniform Pointcloud for SLAM](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=8023504)
![image](https://user-images.githubusercontent.com/46463022/150007536-8ca461bb-28d4-418e-93f0-fc2eea00e0d0.png)
![image](https://user-images.githubusercontent.com/46463022/150007603-a7097a77-a8a4-4df2-9c6d-ace82d60d6be.png)



# Calculating Normals

Fast and Robust 3D Feature Extraction from Sparse Point Clouds, IROS 2016

* High density of points in the cloud is necessary 

  * PFH : Point Feature Histogram
  * VFH : Viewpoint Feature Histogram
  * NARF: Normal Aligned Radial Feature 


* Surface Normal Computation: computed by evaluating the covariance matrix of the Gaussian distribution of all the points that lie in a certain neighborhood of the point.
![image](https://user-images.githubusercontent.com/46463022/153907985-c7143a33-1b5f-4de9-8de6-7eae07712df8.png)



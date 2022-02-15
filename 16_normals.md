# Calculating Normals

Fast and Robust 3D Feature Extraction from Sparse Point Clouds, IROS 2016

* High density of points in the cloud is necessary 

  * PFH : Point Feature Histogram
  * VFH : Viewpoint Feature Histogram
  * NARF: Normal Aligned Radial Feature 


* Surface Normal Computation: computed by evaluating the covariance matrix of the Gaussian distribution of all the points that lie in a certain neighborhood of the point.


* Fast and Robust 3D Feature Extraction from Sparse Point Clouds, IROS 2016

* PCA: Principal Component Analysis
  The resulting variable contains the eigenvectors (named rotation) and their associated eigenvalues (named sdev). Notice the eigenvectors are sorted by their eigenvalues largest to smallest - the first principle component (eigenvector) represents the most variance and the last component the least.
  
  ![image](https://user-images.githubusercontent.com/46463022/154117682-82c417eb-1624-4d96-98fd-a0acc3650e64.png)
  * First eigenvector: green
  * Second eigenvector: blue 
  * Third eigenvector: red
  * The x axis had the most deviation and the z-axis the least.




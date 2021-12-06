#GNSS
## 1- [Improving GNSS Positioning using Neural Network-based Corrections](https://arxiv.org/abs/2110.09581)

### Challenges, of using DNN for GNSS:
1. Poor numerical conditioning caused by large variations in measurements and position values across the globe.   
2. Varying number and order within the set of measurements due to changing satellite visibility  
3. Overfitting to available data.  

### BACKGROUND: DEEP LEARNING ON SETS:
These inputs of varying size and order are commonly referred to as "set-valued inputs"

## 2- [Set Transformer: A Framework for Attention-based Permutation-Invariant Neural Networks_2019](https://arxiv.org/pdf/1810.00825.pdf)\

## 3- [Efficient and Robust LiDAR-Based End-to-End Navigation](https://arxiv.org/pdf/2105.09932.pdf)
* Using only raw 3D point clouds and coarse-grained GPS maps
1. Fast-LiDARNet, an efficient, hardware-aware, and accurate neural network that operates on raw 3D point clouds with accelerated sparse convolution kernels and runs at 11 FPS on NVIDIA Jetson AGX Xavier;
2. Hybrid Evidential Fusion, a novel uncertainty-aware fusion algorithm that directly learns prediction uncer- tainties and adaptively integrates predictions from neigh- boring frames to achieve robust autonomous control;
3. Deployment of our system on a full-scale autonomous vehicle and demonstration of navigation and improved robustness in the presence of sensor failure

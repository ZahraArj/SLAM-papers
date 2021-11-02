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
multi-source data fusion technique

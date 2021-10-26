
# SLAM Backbone

Conventional navigation systems are able to provide either constant-time updates or the ability to incorporate loop closures, but not both. 

**constant-time updates:**
1. EKF-based methods:
  *  Maintain constant-time updates by marginalizing out all past variables   
     *  Variations on the EKF, such as augmented state filters or fixed-lag smoothers, maintain only a subset of the past states to improve estimation accuracy
  *  Fuse the local estimation into the global frame gradually
  *  An accurate initial guess about the transformation between different frames is required to guarantee convergence.
  *  Sensitive to time synchronization: Any late-coming measurements will cause trouble since states cannot be propagated back in filter procedure.
2. Particle Filter (Sequential Monte Carlo)

**Loop Closure:**
* Estimate the value of all past states within the optimization  
* Computational complexity
* ven while leveraging the inherent sparsity of the problem and utilizing the latest algorithms for performing incremental inference, constant-time updates in the presence of loop closures cannot be achieved.

3. Pose Graph
4. Bundle Adjustment

Providing both: **Parallelization**
 * **Basic idea:** have a low-latency process update the current state at a high rate while a slower background process performs ful.
 * **Challenge:**

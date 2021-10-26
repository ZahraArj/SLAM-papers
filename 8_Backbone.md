
# SLAM Backbone

Conventional navigation systems are able to provide either constant-time updates or the ability to incorporate loop closures, but not both. 

1. Pose Graph
2.  EKF-based methods:
  *  Maintain constant-time updates by marginalizing out all past variables
    *  Variations on the EKF, such as augmented state filters or fixed-lag smoothers, maintain only a subset of the past states to improve estimation accuracy and allow the incorporation of measurements involving these additional states.
  *  Fuse the local estimation into the global frame gradually
  *  An accurate initial guess about the transformation between different frames is required to guarantee convergence.
  *  Sensitive to time synchronization: Any late-coming measurements will cause trouble since states cannot be propagated back in filter procedure.



# Calibration
calib.txt: Calibration data for the cameras: 
* P0/P1 are the 3x4 projection matrices after rectification. 
* P0: denotes the left
* P1: denotes the right camera. 
* Tr: transforms a point from velodyne coordinates into the left rectified camera coordinate system.   
In order to map a point X from the velodyne scanner to a point x in the i'th image plane, you thus have to transform it like:

  x = Pi * Tr * X

P0 (3x4): Projection matrix for left grayscale camera in rectified coordinates
P1 (3x4): Projection matrix for right grayscale camera in rectified coordinates
P2 (3x4): Projection matrix for left color camera in rectified coordinates
P3 (3x4): Projection matrix for right color camera in rectified coordinates
R0_rect (3x3): Rotation from non-rectified to rectified camera coordinate system
Tr_velo_to_cam (3x4): Rigid transformation from Velodyne to (non-rectified) camera coordinates
Tr_imu_to_velo (3x4): Rigid transformation from IMU to Velodyne coordinates
Tr_cam_to_road (3x4): Rigid transformation from (non-rectified) camera to road coordinates

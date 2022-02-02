

# Calibration
calib.txt: Calibration data for the cameras: 
* P0/P1 are the 3x4 projection matrices after rectification. 
* P0: denotes the left
8 P1: denotes the right camera. 
* Tr: transforms a point from velodyne coordinates into the left rectified camera coordinate system.   
In order to map a point X from the velodyne scanner to a point x in the i'th image plane, you thus have to transform it like:

  x = Pi * Tr * X

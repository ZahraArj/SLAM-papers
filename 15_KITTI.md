

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


# Technical: [HDL-64E](https://www.wevolver.com/wevolver.staff/hdl-64e.lidar.sensor)
## Specifications
* Diameter 	215	mm
* Height 	283	mm
* Power Consumption 	60 	W
* Operating Voltage 	12 - 32 	V
* Weight	12.7 	kg
* Operating Temperature 	-10 / +60 	C
* Storage Temperature 	-40 / +85 	C
### Sensors 		
* Channels		64
* Measurement Range 	up to 120	cm
* Range Accuracy 	Up to ±2	
* Field of View (Vertical) 	+2.0 to -24.9 	°
* Angular Resolution (Vertical) 	0.4 	°
* Field of View (Horizontal) 	360	°
* Angular Resolution (Horizontal/Azimuth)	0.08– 0.35	
* Rotation Rate 	5 - 20 	Hz
### Laser 		
* Laser Product Classification 		Class 1 Eye-safe
* Wavelength 	903 	nm
### Output		
* 3D LiDAR Data Points Generated 	
  * Single Return Mode 	~1,300,000 points per second
	* Dual Return Mode 	~2,200,000 points per second
* Connection 	100 	Mbps Ethernet Connection
* UDP Packets Contain 		
  * Time of Flight Distance Measurement
  * Intensity Measurement
	* Rotation Angles
	* Synchronized Time Stamps (μs resolution)
* GPS		$GPRMC NMEA Sentence from GPS Receiver 

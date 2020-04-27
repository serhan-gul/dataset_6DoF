We collected motion traces from five users while they were freely interacting with a static virtual object using Microsoft HoloLens. We recorded the users' movements in 6DoF space; i.e., collected position samples (x, y, z) and rotation samples represented as quaternions (qx, qy, qz, qw) where qw is the real (scalar) component of the quaternion. Since the raw sensor data we obtained from HoloLens was unevenly sampled (i.e. different temporal distances between consecutive samples) at 60 Hz, we interpolated the data to obtain temporally equidistant samples. We upsampled the position data using linear interpolation and the rotation data (quaternions) using SLERP. Thus, we obtained an evenly-sampled dataset with a sampling rate of 200 Hz i.e. one sample each 5 ms.

The raw data is formatted as:
<timestamp,x,y,z,qx,qy,qz,qw>

The interpolated data also contains the Euler angles for easier visualisation (although we work solely on quaternions). 
<timestamp,x,y,z,qx,qy,qz,qw,roll,pitch,yaw>

The Euler angles are given in degrees and obtained from the quaternions using intrinsic rotations in ZXY order using the function and parameters: 
> as_euler('ZXY', degrees=True)
Please refer to the Scipy documentation for more details: 
https://docs.scipy.org/doc/scipy/reference/generated/scipy.spatial.transform.Rotation.as_euler.html

For details on our head motion prediction algorithm, please refer to:
"Low-latency Cloud-based Volumetric Video Streaming Using Head Motion Prediction",
Serhan Gül, Dimitri Podborski, Thomas Buchholz, Thomas Schierl, Cornelius Hellge
NOSSDAV'20, Proceedings of the 11th ACM Multimedia Systems Conference (MMSys), 2020

This dataset is free to use for research purposes. If you use this dataset in your research, please cite the above paper.

Serhan Gül
April 2020
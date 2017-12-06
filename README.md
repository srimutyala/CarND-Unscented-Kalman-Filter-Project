# Unscented Kalman Filter Project Starter Code
Self-Driving Car Engineer Nanodegree Program

In this project we utilize an Unscented Kalman Filter to estimate the state of a moving object of interest with noisy lidar and radar measurements. 

[//]: # (Image References)

[ds1]: ./UKF-DS1.JPG.jpg "ds1"
[ds2]: UKF-DS2.JPG.JPG "ds2"

## Basic Build Instructions

1. Clone this repo.
2. Make a build directory: `mkdir build && cd build`
3. Compile: `cmake .. && make`
4. Run it: `./UnscentedKF` Previous versions use i/o from text files.  The current state uses i/o
from the simulator.

## Project Sepcification

### Accuracy
The algorithm needs to satisy the px, py, vx, vy RMSE of [.09, .10, .40, .30]. We manage to achieve a better accuracy than this threshold on dataset 1. However on the dataset 2, the vx is slightly over the required threshold but the remaiing parameters are inline with what's needed.

Dataset 1 RMSE: [0.0686, 0.0829, 0.3324, 0.2331]
Dataset 2 RMSE: [0.0679, 0.0686, 0.5846, 0.2463]

![alt text][ds1]![alt text][ds2]

### Algorithm Design
The algorithm is based on the concepts from the lecture videos and notes. It initilaizes the state vectors and covariance matrcies along with setting the process noise and mesaurement noise. The give defualt proces noise parameters are intentionally inaccurate. Setting these values to more reasonable (what a car/bicycle in a similar position can achieve in terms of velocity and steer) brings the RMSE under the required values.


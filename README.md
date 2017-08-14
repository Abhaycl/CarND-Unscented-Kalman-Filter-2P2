# Extended Kalman Filter Project Starter Code

In this project you will utilize a kalman filter to estimate the state of a moving object of interest with noisy lidar and radar measurements. Passing the project requires obtaining RMSE values that are lower that the tolerance outlined in the project rubric. 

<!--more-->

[//]: # (Image References)

[image1]: /build/result.jpg "Sample final score"

#### How to run the program

```sh
1. mkdir build
2. cd build
3. cmake ..
4. make
5. ./ExtendedKF
6. and run the simulator
```

The summary of the files and folders int repo is provided in the table below:

| File/Folder           | Definition                                                                                    |
| :-------------------- | :-------------------------------------------------------------------------------------------- |
| src/FusionEKF.cpp     | Initializes the Kalman Filter, prepare the Q and F matrices for the prediction step, and call |
| src/FusionEKF.h       | the radar and lidar update functions                                                          |
| src/kalman_filter.cpp | Defines the Predict(), Update(), and UpdateEKF() functions for lidar y radar.                 |
| src/kalman_filter.h   |                                                                                               |
| src/tools.cpp         | Contains the functions that calculate root mean squared error (RMSE) and the Jacobian matrix. |
| src/tools.h           |                                                                                               |
| src/main.cpp          | Has several functions within main(), communicates with the Term 2 Simulator receiving data    |
|                       | measurements, calls a function to run the Kalman filter, calls a function to calculate RMSE   |
|                       | these all handle the uWebsocketIO communication between the simulator and it'sself.           |
|                       |                                                                                               |
| src                   | Folder where are all the source files of the project.                                         |
| build                 | Folder where the project executable has been compiled.                                        |
|                       |                                                                                               |


---

Note that the programs that need to be written to accomplish the project are src/FusionEKF.cpp, src/FusionEKF.h, kalman_filter.cpp, kalman_filter.h, tools.cpp, and tools.h

The program main.cpp has already been filled out, but feel free to modify it.

Here is the main protcol that main.cpp uses for uWebSocketIO in communicating with the simulator.


INPUT: values provided by the simulator to the c++ program

["sensor_measurement"] => the measurement that the simulator observed (either lidar or radar)


OUTPUT: values provided by the c++ program to the simulator

["estimate_x"] <= kalman filter estimated position x
["estimate_y"] <= kalman filter estimated position y
["rmse_x"]
["rmse_y"]
["rmse_vx"]
["rmse_vy"]

---

Extended Kalman Filter Produces results as the x-position is shown as 'px', y-position as 'py', velocity in the x-direction is 'vx', while velocity in the y-direction is 'vy'. Residual error is calculated by mean squared error (MSE).

![Final score][image1]

---

#### Discussion

Could improve the parametrization and analyze all cases in which it could be divided by 0 to obtain a better result.

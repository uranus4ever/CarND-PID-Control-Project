# CarND-Controls-PID

## Overview

This project is to use PID controller to control the steering angle and throttle for driving a car autonomously in a simulator. The simulator provides cross-track error (CTE) via websocket.

Demo: Self driving with PID controller

![gif][gif]

## Discussion on parameters of PID

**Description of PID values in PID control**

 - P (proportional) accounts for present values of the error. For example, if the error is large and positive, the control output will also be large and positive.
 - I (integral) accounts for all past values of the error. For example, if the current output is not sufficiently strong, the integral of the error will accumulate over time, and the controller will respond by applying a stronger action.
 - D (differential) accounts for possible future trends of the error, based on its current rate of change.

**Finally parameters**

* PID parameters used for steering angles:

    * p value: 0.1
    * i value: 0.001
    * d value: 4
    
    
* PID parameters used for throttle:

    * p value: 0.1
    * i value: 0.0001
    * d value: 0.1
    
**How to tune the parameters**

The parameters are tuned manually with the order of: p, d, i. The d and i are first setted to be zeros, and 0.2 is used for the p value. I adjust the p value up and down till it could drive around the first corner and hard to imporve more. Then I keep the p value as it is, and increase the d value. Use the same approach for d value and i value.

In order to automatically fine tune the parameters, an optimization algorithm twiddle can be used, [Twiddle sample code in python](https://martin-thoma.com/twiddle/).
 
## Dependencies

* cmake >= 3.5
 * All OSes: [click here for installation instructions](https://cmake.org/install/)
* make >= 4.1(mac, linux), 3.81(Windows)
  * Linux: make is installed by default on most Linux distros
  * Mac: [install Xcode command line tools to get make](https://developer.apple.com/xcode/features/)
  * Windows: [Click here for installation instructions](http://gnuwin32.sourceforge.net/packages/make.htm)
* gcc/g++ >= 5.4
  * Linux: gcc / g++ is installed by default on most Linux distros
  * Mac: same deal as make - [install Xcode command line tools]((https://developer.apple.com/xcode/features/)
  * Windows: recommend using [MinGW](http://www.mingw.org/)
* [uWebSockets](https://github.com/uWebSockets/uWebSockets)
  * Run either `./install-mac.sh` or `./install-ubuntu.sh`.
  * If you install from source, checkout to commit `e94b6e1`, i.e.
    ```
    git clone https://github.com/uWebSockets/uWebSockets 
    cd uWebSockets
    git checkout e94b6e1
    ```
    Some function signatures have changed in v0.14.x. See [this PR](https://github.com/udacity/CarND-MPC-Project/pull/3) for more details.
* Simulator. You can download these from the [project intro page](https://github.com/udacity/self-driving-car-sim/releases) in the classroom.

There's an experimental patch for windows in this [PR](https://github.com/udacity/CarND-PID-Control-Project/pull/3)

## Basic Build Instructions

1. Clone this repo.
2. Make a build directory: `mkdir build && cd build`
3. Compile: `cmake .. && make`
4. Run it: `./pid`. 

[//]: # (Image References)
[gif]: ./extra/demo.gif


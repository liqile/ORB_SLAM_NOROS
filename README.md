#ORB_SLAM_NOROS

ORB_SLAM_NOROS is a none-ros version of [ORB_SLAM](https://github.com/raulmur/ORB_SLAM). 

Thanks for the author [raulmur](https://github.com/raulmur) of providing the [ORB_SLAM](https://github.com/raulmur/ORB_SLAM)
code. [ORB_SLAM](https://github.com/raulmur/ORB_SLAM) is a very good monocular slam algorithm

##1.Download the code

$mkdir slam

$cd slam

$git clone git@github.com:liqile/ORB_SLAM_NOROS.git

##2.build

###2.1 dependencies

###2.2 build g2o

$cd ~/slam/ORB_SLAM_NOROS/Thirdparty/g2o/

$mkdir build

$cd build

$cmake ..

$make

###2.3 build DBoW2

$cd ~/slam/ORB_SLAM_NOROS/Thirdparty/DBoW2/

$mkdir build

$cd build

$cmake ..

$make

###2.4 build the whole project

before build the project, you may have to change the code in `Tracking.cc`

in the function `void Tracking::run()`, the absolute path of image data, the number of image data, as well as the type 

of image file is defined. You can change them of your own need. after changing the code, you can begin building with

following commands

$cd ~/slam/ORB_SLAM_NOROS/

$mkdir build

$cd build

$cmake ..

$make

###2.5 run

$cd ~/slam/ORB_SLAM_NOROS/bin

$./Project

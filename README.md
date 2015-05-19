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

$sudo apt-get install libboost-all-dev 

$sudo apt-get install libsuitesparse-dev

$sudo apt-get install libblas-dev

$sudo apt-get install liblapack-dev

$sudo apt-get install libeigen3-dev

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

before build the project, you may have to change the code in `Tracking.cc`. in the function `void Tracking::run()`, the absolute path of image data, the number of image data, the names of the image files, as well as the type of image files is defined. You can change them of your own need. after changing the code, you can begin building with following commands

$cd ~/slam/ORB_SLAM_NOROS/

$mkdir build

$cd build

$cmake ..

$make

##3. run

###3.1 check

please check you have the image data with correct type, names and path as you changed the code in `void Tracking::run()`, as mentioned in 2.4

then, you should extract the "visual words" file by typing following commands

$cd ~/slam/ORB_SLAM_NOROS/Data

$unzip ORBvoc.yml.tar.gz

Also, you should change the settings file, it will told the program the calibration parameters of your camera

$cd ~/slam/ORB_SLAM_NOROS/Data

$vim Settings.yaml

###3.2 run

After the operations before, you can run the program

$cd ~/slam/ORB_SLAM_NOROS/bin

$./Project

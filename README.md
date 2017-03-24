# acura

# first download all the package in email, like:

velodyne, pointgrey_camera, mtig_driver, rosserial, kvaser_canlib, newest version flycapture2-2.9.3.43-amd64, MT_Software_Suite_Linux_4.7, xsens_mt-master


velodyne dep install:
rosdep install velodyne_pointcloud

flycapture setup:
1. sudo apt-get install libraw1394-11 libgtkmm-2.4-1c2a libglademm-2.4-1c2a libgtkglextmm-x11-1.2-dev libgtkglextmm-x11-1.2 libusb-1.0-0 libglademm-2.4-dev
2. sudo sh install_flycapture.sh

MT SDK setup:
1. sudo apt-get install realpath && sudo apt-get install sharutils
2. sh ./mtsdk_linux_4.7.sh

xsens_mt-master build and setup:
make


# PAY ATTENTION:
MT_Software_Suite_Linux_4.7 has some update which is conflicted with old version, some function is old and delete.

changes:

SensorData.cpp, line 106:

		```XsMessage msg ;//= packet.originalMessage();```
    
		```==> packet.setMessage(msg);```

line 223:

		```==>if(packet.containsStatus() ){ ROS_INFO_THROTTLE(THROTTLE_VALUE, "Status");}```


serialKey.cpp, ```int setSerialKey()```, comment this function content.

catkin_make all the packages.

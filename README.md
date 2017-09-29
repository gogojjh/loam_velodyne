![Screenshot](/capture.bmp)
Sample map built from [nsh_indoor_outdoor.bag](http://www.frc.ri.cmu.edu/~jizhang03/Datasets/nsh_indoor_outdoor.bag) (opened with [ccViewer](http://www.danielgm.net/cc/))

:white_check_mark: Tested with ROS Indigo and Velodyne VLP16. [(Screencast)](https://youtu.be/o1cLXY-Es54)

All sources were taken from [ROS documentation](http://docs.ros.org/indigo/api/loam_velodyne/html/files.html)

Ask questions [here](https://github.com/laboshinl/loam_velodyne/issues/3).

How to build with catkin:

```
$ cd ~/catkin_ws/src/
$ git clone https://github.com/laboshinl/loam_velodyne.git
$ cd ~/catkin_ws
$ catkin_make -DCMAKE_BUILD_TYPE=Release 
$ source ~/catkin_ws/devel/setup.bash
```

Running:
```
roslaunch loam_velodyne loam_velodyne.launch
```

In second terminal play sample velodyne data from [VLP16 rosbag](https://db.tt/t2r39mjZ):
```
rosbag play ~/Downloads/velodyne.bag 
```

Or read from velodyne [VLP16 sample pcap](https://midas3.kitware.com/midas/folder/12979):
```
roslaunch velodyne_pointcloud VLP16_points.launch pcap:="/home/laboshinl/Downloads/velodyne.pcap"
```

---
[Quantifying Aerial LiDAR Accuracy of LOAM for Civil Engineering Applications.](https://ceen.et.byu.edu/sites/default/files/snrprojects/wolfe_derek.pdf) Derek Anthony Wolfe

[ROS & Loam_velodyne](https://ishiguro440.wordpress.com/2016/04/05/%E5%82%99%E5%BF%98%E9%8C%B2%E3%80%80ros-loam_velodyne/) 


### in git
To run the program, users need to download the code from GitHub, or follow the link on the top of this page. The program can be started by ROS launch file (available in the downloaded folder), which starts four nodes and rivz:
```
roslaunch loam_velodyne.launch
```

Datasets are available for download from here, or at the bottom of this page. Please make sure the data files are for the Velodyne version (not back and forth spin or continuous spin version). With the program running (from the launch file), users can play the data file:
```
rosbag play data_file_name.bag
```

Note that if a slow computer is used, users can try to play the data file at a low speed, e.g. play the data file at half speed:
```
rosbag play data_file_name.bag -r 0.5
```


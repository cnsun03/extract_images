extract_images
=======

This package was edited starting [image_view][1] and [image_transport][2] to extract images from multiples cameras in ROS bags.

## Build
To build this package, clone it in your workspace, then just type the command below:
```
$ catkin build extract_images
```

## Items to check
Before running the code, check if the launch file `export_image.launch` is configured in the way you need. Make sure that the topics are the topics that are you looking for. As well, make sure that the others parameters are set up as you needed.


## Extract raw images
To extract raw images, do the following steps in order:
1. Open a terminal and run roscore;
2. In other terminal, go to the directory which the bags are stored and run the following command (this command will make all the bag files in directory run in order):

```
$ rosbag play *.bag
```

3. In order terminal run the roslaunch:
```
$ roslaunch extract_images export_image.launch
```

## Extract compressed images
To extract compressed images it's necessary to perfom a taks more to be possible extract the images. So, to do this, follow the steps below:

1. Open a terminal and run roscore;
2. In other terminal, go to the directory which the bags are stored and run the following command (this command will make all the bag files in directory run in order):

```
$ rosbag play *.bag
```
3. In other terminal run the command (this sould be done for each topic):
```
$ rosrun image_transport republish compressed in:="/topic" raw out:="/new_topic"
```

For example:
```
$ rosrun image_transport republish compressed in:=/spot2/camera_front/color/image_raw_throttle/ raw out:=/spot2/camera_front/color/image
```

4. In other terminal run the roslaunch:
```
$ roslaunch extract_images export_image.launch
```

## Usefull commands
To remove the "`count%04i_`" from the file names, install the library rename from Linux, by the command:
```
$ sudo apt install rename
```

Then, type the command:
```
$ rename 's/count[0-9][0-9][0-9][0-9]_//' *
```

Other useful commands are available in the file `commands.txt`.

## More information
More information can be found in Wiki ROS.




[1]: https://github.com/ros-perception/image_pipeline/tree/noetic/image_view
[2]: http://wiki.ros.org/image_transport

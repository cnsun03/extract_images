extract_images
=======

This package was edited starting [image_view][1] and [image_transport][2] to extract images from multiples cameras in ROS bags.

Edited for D455

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
2. Edit the bag file location in export.launch, and edit anything else that needs to be edited

3. Run the roslaunch:
```
$ roslaunch extract_images export.launch
```

## More information
More information can be found in Wiki ROS.




[1]: https://github.com/ros-perception/image_pipeline/tree/noetic/image_view
[2]: http://wiki.ros.org/image_transport

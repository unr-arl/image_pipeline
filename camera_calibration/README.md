# Images - Point cloud data acquisition
Make use of ROS-Toolbox, then collect point cloud from (LiDAR or picoflexx) in parallel with images.Note: copy archive file in "\tmp" folder after finishing because computer may delete all files in tmp folder automatically.

* Change the lidar topic name in source code (Search: "tung-topic-name")

* Change the sync time in source code (Search: "tung-sync-time")

* For small checker board:
rosrun camera_calibration cameracalibrator.py --size 7x6 --square 0.0675 right:=/cam1/image_raw left:=/cam0/image_raw left_camera:=/cam0 right_camera:=/cam1 --no-service-check

* For big checker board:
rosrun camera_calibration cameracalibrator.py --size 8x6 --square 0.145 right:=/cam1/image_raw left:=/cam0/image_raw left_camera:=/cam0 right_camera:=/cam1 --no-service-check

# Single camera:
*small:
rosrun camera_calibration cameracalibrator.py --size 7x6 --square 0.0675 image:=/cam0/image_raw camera:=/cam0

*big:
rosrun camera_calibration cameracalibrator.py --size 8x6 --square 0.145 image:=/cam0/image_raw camera:=/cam0

--square 4.25 inches 
rosrun camera_calibration cameracalibrator.py --size 8x6 --square 0.108 right:=/ptgrey_node/right/image_raw left:=/ptgrey_node/left/image_raw left_camera:=/ptgrey_node/left right_camera:=/ptgrey_node/right --no-service-check

rosrun camera_calibration cameracalibrator.py --size 8x6 --square 0.108 image:=/camera/image_mono camera:=/camera --no-service-check pcl:=/velodyne_points

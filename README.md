Create workspace in ros2:
ros2 pkg create --build-type ament_cmake <package_name>


Clear colcon path:
unset COLCON_PREFIX_PATH
unset AMENT_PREFIX_PATH
unset CMAKE_PREFIX_PATH


To use SLAM on Testbed:
ros2 launch my_bot launch_sim.launch.py world:=./src/my_bot/worlds/test3.world   //Gazebo 

rviz2 -d src/my_bot/config/costmap.rviz                 //rviz with costmap

ros2 launch my_bot navigation_launch.py use_sim_time:=true       //nav2

//SLAM

ros2 launch slam_toolbox online_async_launch.py      params_file:=./src/my_bot/config/mapper_params_online_async.yaml use_sim_time:=true   

Launch my_bot in rviz:
rviz2 -d src/my_bot/config/laser_scan.rviz

Launch teleop twist keyboard:
ros2 run teleop_twist_keyboard teleop_twist_keyboard 

To open bash rc:
gedit ~/.bashrc

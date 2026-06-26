# ROS2-Jazzy-Gazebo-Learnings
---

## Launch Files 

Launch files are a way in ROS to automate the process of running a particular set or sequence of nodes, services, actions etc.

Instead of running several ros2 shell commands across several terminals all of them can be handled in a sequence using a launch file

ROS - 1 -- Launch Files were written as .xml files
ROS - 2 -- launch and launch_ros python packages for creating launch files as python scripts 

### Details of Launch file libraries

**Launch Management**

* *LaunchDescription* - This container with nodes, arguments, actions is returned by the script.launch.py file to describe.

* *IncludeLaunchDescription* - Include and run another launch file from this

    * *PythonLaunchDescriptionSource* - Helper function to *IncludeLaunchDescription* to tell how to parse included file

**Arguments, Configurations and Conditions**

* *DeclareLaunchArgument* - To define a commandline input parameter for launch file
* *LaunchConfiguration* - Reference pointer to a declared launch argument
* *IfCondition* - Conditional wrapper to decide on launching some task

**Nodes and Parameters**

* *Node* - To create ROS2 Node
* *ParameterValue* - Wrapper to handle complex parameter types

**Substitutions and Path Helpers**

* *PathJoinSubstitution* - waits until runtime, platform independent
* *Command* - Executes sell command and takes standard output as a string
* *FindExecutable* - Locates path of external program so Command or Node can execute it regardless fo where it is installed on user machine
* *get_package_share_directory* - Absolute path to the "share" folder of an installed ROS2 package on computer
---

## Why colcon build ?

* Seperating src from install ensures that running code doesnt alter or litter the original source code. This is a standard practice in SDE

* colcon build creates these working files. Adding --symlink-install arguement makes it automated for python or config script tweaks but for c++ code build needs to be re run

* build folder is for storing temporary object files .o and config caches, intermediary build scripts

* install folder has final executable version of software

* log is a diary of build process to debug the build process with time stamps
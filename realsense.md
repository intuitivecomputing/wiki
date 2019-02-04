# RealSense Tutorial
## Last updated by [Gopika Ajaykumar](https://github.com/gopikaajaykumar) on 02/04/19

At this time, all RealSense cameras in our lab are from the Intel® RealSense™ Depth Camera D400-Series, which basically means
that they use stereo vision to calculate depth. More information about the specifications and differences between the different camera models owned by the lab can be found [here](https://software.intel.com/en-us/realsense/d400).

### Installation
In order to use the RealSense cameras with ROS, the [realsense2_camera package](https://github.com/intel-ros/realsense) 
should be used. Installation instructions for this package and its pre-requisites are detailed on its GitHub (linked above). 
To summarize, you will have to:
1. Install the RealSense SDK (librealsense). Make sure that you install version two, and not version one, as this is the 
version supporting the D400-Series. The realsense2_camera github README details the installation process.
2. Clone the realsense2_camera package (found [here](https://github.com/intel-ros/realsense/releases)) into your desired catkin 
workspace. Note that if you ever use a RealSense camera that is not in the D400-Series and is also not an SR300 model, then you 
will have to use version 1 of the realsense package (the latest build can be found [here](https://github.com/intel-ros/realsense/releases/tag/1.8.1)). I recommend cloning the latest release.

### Usage
Usage instructions are provided in the realsense2_camera GitHub README under "Usage Instructions." This covers how to launch the primary launch files in this package. It also provides information on how to configure camera control values, how to run multiple RealSense cameras on an individual or networked system, and how to use some of the provided post-processing filters. 


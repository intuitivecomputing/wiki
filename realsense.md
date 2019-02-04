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

You can also view the sensor data from the camera outside of ROS by running "realsense-viewer" on the terminal, provided you successfully installed librealsense.

### Potential Problems
Known issues for the ROS RealSense package can be seen in the realsense2_camera GitHub README under "Known Issues." If you manually installed librealsense and are having issues running the ROS RealSense package, consulting "Troubleshooting Installation and Patch-related Issues" under [this link](https://github.com/IntelRealSense/librealsense/blob/development/doc/installation.md) may be helpful.

From my experience, some of the issues you may encounter include the following:
1. **You are unable to retrieve sensor data from the camera, both with the ROS RealSense package and with the realsense-viewer. ("Frames not arriving within 5 seconds")** First, as always, try unplugging and plugging in again. This works occasionally (especially if you're using an extension cable, which the RealSense cameras usually don't play well with due to their strict power requirements.) Be sure you're using a USB 3 (Super Speed) cable/port. USB 2 will NOT work (unless you're really lucky, and even in that case it probably won't be reliable.)
This could mean that you need to upgrade (or in rare cases downgrade) your camera firmware. Each RealSense ROS package release details its supported firmware for each camera model. You should consult this to make sure you are running the correct firmware for your particular release. If you find that you need to upgrade the camera firmware, details on how to do this can be found [here](https://www.intel.com/content/www/us/en/support/articles/000028171/emerging-technologies/intel-realsense-technology.html). If you don't want to update the firmware, downgrading to an older version of the RealSense package is another option (I recommend always keeping the firmware up-to-date, though.) Another potential issue could be that the release that you are using does not support your current Linux kernel (supported kernels are listed for each release for your reference.) Only downgrade your kernel as a last resort, and do so carefully. If at all possible, try older versions of the RealSense ROS package that do support your current kernel before attempting to downgrade.

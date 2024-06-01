FROM osrf/ros:${templateOption:distro}-desktop-full

# Upgrade all packages
RUN sudo apt update && sudo apt upgrade -y

# Install essential packages
RUN sudo apt install -y wget

# Rosdep update
RUN rosdep update

# Source the ROS setup file
RUN echo "source /opt/ros/${ROS_DISTRO}/setup.bash" >> ~/.bashrc

################################
## ADD ANY CUSTOM SETUP BELOW ##
################################
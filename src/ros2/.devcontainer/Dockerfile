FROM osrf/ros:${templateOption:distro}-desktop-full

# Upgrade all packages
RUN sudo apt update && sudo apt upgrade -y

# Install essential packages
RUN sudo apt install -y wget

# Create overlay workspace
WORKDIR /root/ros_ws/src

RUN if [ -z "${templateOption:packageURL}" ]; then \
        git clone ${templateOption:repoUrl}; \
        cd ..; \
        rosdep install --from-paths src --ignore-src -r -y; \
        colcon build; \
    fi


# # Source the ROS setup file
# RUN echo "source /opt/ros/${ROS_DISTRO}/setup.bash" >> ~/.bashrc
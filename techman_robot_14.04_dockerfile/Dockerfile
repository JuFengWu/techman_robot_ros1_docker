FROM dorowu/ubuntu-desktop-lxde-vnc:trusty
LABEL maintainer "leowu102000@gmail.com"

#install git
RUN apt-get update
RUN echo "y" | apt-get install git 

#install vim
RUN echo "y" | apt-get install vim

#install ros
RUN apt-get update && apt-get install -y wget && rm -rf /var/lib/apt/lists/*
RUN sh -c 'echo "deb http://packages.ros.org/ros/ubuntu trusty main" > /etc/apt/sources.list.d/ros-latest.list'
RUN wget https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -O - | sudo apt-key add -
RUN apt-get update
RUN echo "y" | apt-get install ros-indigo-desktop-full

#install techman robot ros
RUN mkdir -p /root/ws_techman_robot/src
RUN cd /root/ws_techman_robot/src && git clone https://github.com/kentsai0319/techman_robot.git


RUN echo "y" | apt-get install ros-indigo-effort-controllers
RUN echo "y" | apt-get install ros-indigo-joint-state-controller
RUN echo "y" | apt-get install ros-indigo-ros-control 
RUN echo "y" | apt-get install ros-indigo-ros-controllers
RUN echo "y" | apt-get install ros-indigo-moveit

#build it
RUN /bin/bash -c "source /opt/ros/indigo/setup.bash && cd /root/ws_techman_robot && catkin_make"
RUN /bin/bash -c "echo 'source /root/ws_techman_robot/devel/setup.bash' >> /root/.bashrc"

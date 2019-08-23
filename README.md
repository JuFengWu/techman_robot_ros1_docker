# techman_robot 

A driver provides ROS support for techman robots in docker. 
You can just install docker and run it on docker container.


## Getting started(linux)
---
The fastest way is download from Docker hub. If you do'nt have Docker, you can go to [here](https://www.docker.com/) following the instructions to download Docker. 
Once you have docker, please follow those steps to download and run 
1. Typing

```
sudo docker run -it --name techman_robot_ros leowu102000/techman_robot_14.04_ver
``` 
2. Open browser and navigate to localhost:6080
3. The source code will be at /root/ws_techman_robot

## Restart 
The next time you want to restart this container you cab just run:
```
sudo docker start techman_robot_ros
```
and open broswer to localhost:6080

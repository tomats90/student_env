# ros_env_vscode_webviz
----------------------------

Origin:
- https://github.com/devrt/ros-devcontainer-vscode
- https://github.com/cruise-automation/webviz

Packed with:
- Pre-configured docker image for ROS development.
- Browser accessible X11 server to display gazebo, rviz, rqt (runs on Windows/Mac).
- Tasks definition to run catkin_make, roscore, rviz commands.
- Preconfigured code completion for C++, Python, XML (package.xml, launchfiles, URDF, SDF).
- Preconfigured simulation environments (Flatland, TurtleBot3, ARIAC, Virtual RobotX, UUV).
- Bonus: WebIDE (Theia) with preconfigured C++, Python, XML completion.
- Webviz

Requirements
-------------------------------------
Before you start you have to have docker and docker-compose installed on your machine. If not, install using:

1. Ubuntu:
```shell
$ sudo apt-get install docker docker-compose
```

2. On Mac Docker-compose should be part of docker Desktop, if not, use the following gude https://docs.docker.com/docker-for-mac/install/
3. On Windows one needs to install Docker desktop https://docs.docker.com/docker-for-windows/install/
    * Docker uses feature cgrous from linux Kernel, so installing Docker desktop, it virtualises a Linux Kernel. To virtualise in Windows, one hast to conduct the  following steps:
    * check if the parameters in the following link apply: https://docs.docker.com/docker-for-windows/troubleshoot/#virtualization
    * most important is in task manager: <img src="https://user-images.githubusercontent.com/48677890/110318061-4d9d0b80-800d-11eb-8793-b4c5af963cef.png" width="500" height="500">
    * if the virtualisation is deactivated, then it needs to be enables in BIOS
    * check in google how to enable for your hardware. Here is an example for ASUS (used the manual from https://www.asus.com/support/FAQ/1038245/) <img src="https://user-images.githubusercontent.com/48677890/110318487-d451e880-800d-11eb-9fdb-dddb2757917c.png" width="500" height="500">




How to use the WebIDE 
-------------------------------------
As of writing, docker-compose support of VSCode is not perfectly stable on all the platforms.
We recommend using Theia WebIDE since it has complete VSCode function support after 1.0 release.

1. Clone this repository:
```shell
$ git clone https://gitlab.switch.ch/digital_engineering/ros_env_vscode_webviz.git
```

2. In the file "docker-compose.yml" line 44, set your local shared folder. Before the next step put there a bagfile.

3. Enter the following command under the folder of the cloned project:
```shell
$ cd ros_env_vscode_webviz
$ docker-compose up
```
If you run this command for the first time, it will download lots of data and run for a long time => take a coffee :)
Once the command has completed start up the environment:

4. Open http://localhost:3001/ to get VS Code using your favorite browser.

5. Open http://localhost:3003/ to get webviz using your favorite browser.

6. To playback your bagfile from your shared folder:
    - in VS Code open terminal and write: 
    ```shell
    $ rosrun rosbridge_server rosbridge_websocket 
    ```    
    - in VS Code open 2nd terminal and write: 
    ```shell
    $ rosrun rosapi rosapi_node
    ```   
    - in VS Code open 3rd terminal, navigate to bagfile path and play bagfile: 
    ```shell
    $ cd ..
    $ cd bagfiles
    $ rosbag play YourBagFile.bag
    ```    

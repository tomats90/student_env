# Student Environment
----------------------------

Packed with:
- Browser accessible X11 server to display stuff.
- VS Code WebIDE
- packages
    - gcc, cmake
    - python, pip

Requirements
-------------------------------------
Before you start you have to have docker and docker-compose installed on your machine. If not, install using:

1. Ubuntu:
```shell
$ sudo apt-get update
$ sudo apt-get install docker docker-compose
```

2. On Mac Docker-compose should be part of docker Desktop, if not, use the following gude https://docs.docker.com/docker-for-mac/install/
3. On Windows one needs to install Docker desktop https://docs.docker.com/docker-for-windows/install/
    * Docker uses feature cgrous from linux Kernel, so installing Docker desktop, it virtualises a Linux Kernel. To virtualise in Windows, one hast to conduct the  following steps:
    * check if the parameters in the following link apply: https://docs.docker.com/docker-for-windows/troubleshoot/#virtualization
    * most important is in task manager: <img src="https://user-images.githubusercontent.com/48677890/110318061-4d9d0b80-800d-11eb-8793-b4c5af963cef.png" width="500" height="500">
    * if the virtualisation is deactivated, then it needs to be enables in BIOS
    * check in google how to enable for your hardware. Here is an example for ASUS (used the manual from https://www.asus.com/support/FAQ/1038245/) <img src="https://user-images.githubusercontent.com/48677890/110318487-d451e880-800d-11eb-9fdb-dddb2757917c.png" width="500" height="500">




How to use the student environment 
-------------------------------------

1. Clone this repository:
```shell
$ git clone https://github.com/tomats90/student_env.git
```

2. Enter the following command under the folder of the cloned project:

    Linux
    ```shell
    $ cd student_env
    $ sudo docker-compose up
    ```

    Windows powershell

    ```powershell
    $ cd student_env
    $ docker-compose up
    ```

If you run this command for the first time, it will download lots of data and run for a long time => take a coffee :)
Once the command has completed start up the environment:

3. X11 VNC server http://localhost:3000/

4. VS Code http://localhost:8080/ (password: password)

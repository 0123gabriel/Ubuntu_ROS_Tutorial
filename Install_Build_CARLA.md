# Tutorial to Build CARLA in Ubuntu 22.04. 

This method to install CARLA will let you create and try your own maps and vehicles. If you are OK with predetermined maps and vehicles, you should go to the other CARLA tutorial. 

To check for more information during the installation, you can check *Build CARLA in Linux* website (https://carla.readthedocs.io/en/latest/build_linux/). Also, if you are using another Ubuntu version, the given link will help you. 

## Requirements to Build CARLA in your computer.

### System requirements
* ***Ubuntu version:*** CARLA is supported by Ubuntu versions from 16.04 until 22.04. Make sure that you have a proper Ubuntu version to let Unreal Engine work properly. To check your ubuntu version, you can run this in the terminal.

```bash
cat /etc/issue
```

After that, you will know your Ubuntu version.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/ace9d996-025a-487d-ae78-3cde43e704b2)

* ***130 GB disk space:*** CARLA will take aorund 30GB and Unreal Engine around 91GB, so you will need 130GB approximately taking into account extra programs to use this simulation software. To check your disk free-space, runt his command.

```bash
df -h /home
```

The putput shoul be something like this.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/d17af7b1-d375-4ffc-bb28-0423867d21e0)

* ***An adequate GPU:*** You will need at least 6GB GPU, but 8GB GPU is recommended. Also, a dedicated GPU is highly useful for Machine Learning. To check your GPU capabilities, you should run this (This will only help if you have NVIDIA GPU, and the drivers are correctly installed).

```bash
nvidia-smi
```

The output shoul be something like this. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/5812cfa5-dd30-4d9a-a56e-d3dd4acc202d)

In the center of the table, you will see your GPU size. In this case, my GPU has 8GB. If you do not have NVIDIA GPUs, you should go to the other tutorial to see more information about Intel Graphics Cards, but CARLA versions after 0.9.12 will need Vulkan drivers that are NIVIDIA exclusive, but, either way, you might be able to run CARLA, installing those drivers. 


* ***Two TCP ports and good internet connection:*** 2000 and 2001 by default. Make sure that these ports are not blocked by firewalls or any other applications. To see your available TCP ports, run this command.

```bash
sudo netstat -plnt
```

The output should something like this. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/09abc7ca-2489-439e-bb0b-7d3d9ee774b7)

If when you run the previous command, you get a message saying that Ubuntu do not recognizes that command, and it will recommend you to install net-tools, do it by this command. 

```bash
sudo apt-get install net-tools
```

### Software requirements

* ***Python:*** You will need to have python2 and python3 installed in your computer. But, if you are using virtual environments, that would work too for this tutorial. To check about virtual environments, scroll all the way down and you will see a small explanation about them, and also how to install an app to manage virtual environments; you can also follow the tutorial and make the virtual environments later, I would recommend to follow the tutorial in its order.

Most of the Ubuntu OS come with python3, and you can check that by running this command

```bash
python3 --version
```

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/05604f65-7432-4cf7-8479-542f720fc171)

But, python2 might not be installed during Ubuntu installation, but to be sure, you can check that by running this. 

```bash
python --version
```

If you do not have python2, you will have this output

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/35a6c32f-160d-4147-99ed-bb236d40c671)

So, to install pyhton2, run this commands in the terminal.

```bash
sudo apt update
```

```bash
sudo apt install python2
```

After the last command you will be asked to install or no Python, please type *Y* and press enter. Once you have python2 installed, you will get this after running ```python --version ```

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/98511bf0-aba5-4bde-ba67-4c324d1e0e4e)

* ***pip:*** CARLA will need to install some python packages, and to do that, you must have pip or pip3 versions >= 20.3. To check if you have pip or pip3, run this commands in ther terminal. 

This for pip (python2)
```bash
pip --version
```

This for pip3 (python3)
```bash
pip3 --version
```

If you already have pip, please upgrade it and to do that read the third command from here. But, if you do not have it, run this to install **pip**. You might be asked to type *Y* to install it, please do it and press enter. 

```bash
curl 'https://bootstrap.pypa.io/pip/2.7/get-pip.py' > get-pip.py && sudo python2 get-pip.py
```

To check your pip verison, run this.

```bash
pip -V
```

The output should be something like this.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/94006f63-9855-4e5e-96f3-8fcdcb272156)

To upgrade pip to the latest version, run this commands. 

```bash
pip install --upgrade pip
```

If you already have pip3, upgrade it by running the third command from here. If you do not have it, to install ***pip3*** run this. You might be asked to type *Y* to install it, please do it and press enter. 

```bash
sudo apt install python3-pip
```

To check the pip3 versions, type this. and the output should be the one show below.

```bash
pip3 -V
```

To upgrade pip3 to the latest version, tun this command.

```bash
pip3 install --upgrade pip
```

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/144f3d1b-a882-428e-a009-0b442f1d5c5c)

* ***CARLA software required:*** CARLA requires some prevoius software installed in your computer. To have them, copy all of the below commands, and paste them in the terminal, then press enter. 

```bash
sudo apt-get update &&
sudo apt-get install wget software-properties-common &&
sudo add-apt-repository ppa:ubuntu-toolchain-r/test &&
wget -O - https://apt.llvm.org/llvm-snapshot.gpg.key|sudo apt-key add
```

Based on your Ubuntu version, run the commands in Build CARLA website (https://carla.readthedocs.io/en/latest/build_linux/). Here I am using Ubuntu 22.04, so the commands below are the ones I need. 

```bash
sudo apt-add-repository "deb http://archive.ubuntu.com/ubuntu focal main universe"sudo apt-add-repository "deb http://archive.ubuntu.com/ubuntu focal main universe"
```

```bash
sudo apt-get update
```

```bash
sudo apt-get install build-essential clang-10 lld-10 g++-7 cmake ninja-build libvulkan1 python python3 python3-dev python3-pip libpng-dev libtiff5-dev libjpeg-dev tzdata sed curl unzip autoconf libtool rsync libxml2-dev git git-lfs
```

To run this one, copy all the commands and paste them in the terminal, and press enter.  

```bash
sudo update-alternatives --install /usr/bin/clang++ clang++ /usr/lib/llvm-10/bin/clang++ 180 &&
sudo update-alternatives --install /usr/bin/clang clang /usr/lib/llvm-10/bin/clang 180 &&
sudo update-alternatives --install /usr/bin/g++ g++ /usr/bin/g++-7 180
```

Then, for all Ubuntu versions, run this commands in the terminal.

``` bash
pip install --user setuptools &&
pip3 install --user -Iv setuptools==47.3.1 &&
pip install --user distro &&
pip3 install --user distro &&
pip install --user wheel &&
pip3 install --user wheel auditwheel
```

Finally, you may need this other libraries. Run this all commands.

```bash
pip install --user pygame numpy &&
pip3 install --user pygame numpy
```

# Unreal Engine Installation

## Connecting GitHub and Epic Games accounts to download Unreal Engine

1. This step requieres a GitHub and a Epic Games account. To create a GitHub account, go to this link (https://github.com/) and click on sign up. To create an Epic Games account, use this link (https://www.epicgames.com/site/es-ES/home) and in the right top corner, click on the profile item, next to the Download button, and register yourself. 

2. Then, go to this wwebsite (https://www.unrealengine.com/es-ES) and log in if required.
3. Go to the profile icon in the right top corner, and a desplegable list will appear, please select Account.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/07d8572f-8cc2-47c1-b1ef-cc4513e29a52)

4. In the sidebar, select APPS AND ACCOUNTS, and click on the ACCOUNTS tab.
5. Click on the Connect button below GitHub icon.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/35e56439-ae88-4315-9a53-08e5a36d51cb)

6. A window will appear, check the box, and the scroll all the way down and click on I AGREE, then click on CONNECT ACCOUNT.
7. In the pop-up window, click on Authorize EpicGames button.
8. Few seconds later, you will recieve to your GitHub registered mail, click on Join @EpicGames button, and then, again, in Join Epic Games button. 

## Installing Unreal Engine

Installing Unreal Engine will requiere to open Files app, and click on Home. Then open this directory on the Terminal by right click in any part except over the folders, and click on Open in the Terminal. 

1. Run the following command to clone the content for CARLA's fork of Unreal Engine 4.26 to your local computer.

```bash
git clone --depth 1 -b carla https://github.com/CarlaUnreal/UnrealEngine.git ~/UnrealEngine_4.26
```

If your run the previous command, and you get a message like this:

```bash
remote: Support for password authentication was removed on August 13, 2021.
```

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/2226d99f-4c08-4623-852d-4286c344edb4)

### -------------------------------------------------------------------------------------------------------------------------------------
### Solve for the last error

1. You have to open your GitHub account, go to settings (clicking on the right top corner, and looking for settings option).
2. In the sidebar, click on Developer settings.
3. In the sidebar, click on Personal access tokens and click on Tokens (classic).
4. Then click on Generate new token button (right side) and select Generate new token (classic), and enter your password.
5. Give a name for the token, it should be related with the reason your are creating it, then select a amount of days for the token expiration (I recommend 30 days), and select the tasks you are going to do with it, o just select all of them (I recommend this one).
6. Click on Generate token, and copy your token and save it in a place you will remember, because you will not see your token again.
7. Run this commands in the terminal.

```bash
git config --global user.name "your_github_username"
```

```bash
git config --global user.email "your_github_email"
```

```bash
git config -l
```

With the last one, you will see your name, and email setted. 

### -------------------------------------------------------------------------------------------------------------------------------------

Now, run again the command in step one, you will be asked for your GitHub username, and then for your password. In the password paste your Personal Acces Token. 

2. Go to the directory where you cloned the repository, by running this. 

```bash
cd ~/UnrealEngine_4.26
```

3. Make the build. This may take an hour or two depending on your system.

```bash
./Setup.sh && ./GenerateProjectFiles.sh && make
```

When the installation is running, a window could appear asking about Unreal Engine types, select Yes.

4. Open the Editor to check that Unreal Engine has been installed properly, do this with this command.

```bash
cd ~/UnrealEngine_4.26/Engine/Binaries/Linux && ./UE4Editor
```

After that command you will see this window, which is while Unreal Engine is initializing. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/9743b9ad-f329-4834-bc10-76d3b97840db)

When Unreal Engine is already initialized, you will watch this.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/c60b9193-a6c4-4abd-a387-20195e7768b2)

5. Close Unreal Engine by clicking the X in the top right corner.
6. Run the following command in the Terminal.

```bash
echo "export UE4_ROOT=~/UnrealEngine_4.26" >> ~/.bashrc
```

The last command will add the the directory of Unreal Engine to the .bashrc file, which will help you with the next part.

# Build CARLA

(Optional) Downloading aria2 with ``` sudo apt-get install aria2 ``` will speed up the following commands.

Build CARLA will requiere to open Files app, and click on Home. Then open this directory on the Terminal by right click in any part except over the folders, and click on Open in the Terminal. 

1. Clone the CARLA repository, to do that, run this command in the terminal. Once the command is executed, CARLA files will be located in the directory you were in when the ``` git clone ``` command was applied. 

```bash
 git clone https://github.com/carla-simulator/carla
```

All the commands after the last one, must be executed in CARLA root folder, which should be the one that was created in the same directory where Download, Pictures, etc folders are, and it should had named as ``` carla ```.

2. Update to the latest CARLA version, which, at the time of running this tutorial, is 0.9.15. This might take 1 or 2 hours. 

```bash
./Update.sh
```

3. Then, compile the Python API client, which has to be done once.

```bash
make PythonAPI
```

4. Then in the CARLA root directory, run the following command.

```bash
cd PythonAPI/carla/dist
```

5. Then, type ``` ls ```, and you will see 2 files. One that has a ``` .egg ``` format and the other one with a ``` .whl ``` format. The ``` .egg ``` file is for CARLA versions prior 0.9.12, and the ``` .whl ``` is for higher versions. Also, ``` .whl ``` format is more current, and have better features than ``` .egg ``` files. Then, to install the ``` .whl ``` format, you have to run the following command. But, before running it, I recommend to create a virtual environment to install it, if you want to do it, read the **Virtual Environment Usage** section and the come back and continue from the step number 5. 

The path to the ``` .whl ``` file, should look like this:

```bash
carla/PythonAPI/carla/dist
```

To install the ``` .whl ``` with python3 run this command

```bash
pip3 install <path/to/wheel>.whl
```

To install the ``` .whl ``` with python2 run this command

```bash
pip install <path/to/wheel>.whl
```

6. To compile the server, run this command. This might take 1 hour depending on your computer hardware.

```bash
make launch
```

Once you have executed the last command, Unreal Editor will open. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/bcf2b901-377d-40c8-a974-686c8aba2cda)

7. The ``` make ``` command compiles different program pieces and builds some final executables, so you have to run it once, and then to avoid building those executables again, and use Unreal Editor faster, you just need to run this command.

```bash
make launch-only
```

As was said, this will open Unreal Editor and you will be able to run the simulation with the Play button located in the upper part, and to stopped it with the Stop button, which should appear where the Play button was before being pressed. Also, you can edit the simulation, and create your own map which is explained in another tutorial. The following video shows how navigate in the map is like, and to do that you have to use the left click to move the camera, and ``` WASD ``` keyboard letters to move yourself. 

https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/d21bab78-6606-4cfc-aa84-e3e0e8bdf3e2

To play with the simulation you can generate vehicles by this bash commands in another Terminal. 

```bash
cd carla/PythonAPI/examples
```

The following command might give some problems that I did not face because I used the virtual environment way, so I am sorry for that, but solve them should not take that much time.  

```bash
python3 -m pip install -r requirements.txt
```

```bash
python3 generate_traffic.py
```

You will see comething like this. Note that I already clicked the Play button in the upper part before recording. 

https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/f6114b5d-16e8-4835-95b8-e7e52c307adb

You can also play with the weather, by running this commands in another Terminal. 

```bash
cd carla/PythonAPI/examples
```

```bash
python3 dynamic_weather.py
```

And finally, if you want to drive a car, type this in another Terminal. Once you do that, in the Terminal will appear how you can use some keyboard letters to control the car, and see more option related with sensors, autonomous navigation, etc. 

```bash
cd carla/PythonAPI/examples
```

```bash
python3 manual_control.py
```

This are the controls:

![Screenshot from 2024-02-24 21-12-09](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/05cf3055-e60f-418d-9b13-cce25bd14f85)

In this video I am playing. It goes a bit slow but it is beacuse I was recording my screen.

https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/ba2354e2-601d-4548-958e-26fc7026d82b

## Virtual Environment Usage

A virtual environment is a space where you can have an specific python version isolated. Virtual environments are strongly recommended to use with every python project you are developing, and it is useful because you will not have any problems with previous installed libraries. To use virtual environments you have 2 options:

1. **Python virtual environment packages:** This package is called ``` virtualenv ``` for python2 and ``` venv ``` for python3.
2. **Anaconda:** Anaconda is a manager of python virtual environments, and in this tutorial I will use this option because it is the most used across the industry and academy. And, after using Python virtual environment packages and anaconda, I think Anaconda is easier.

## Installing Anaconda

1. Go to the following link (https://www.anaconda.com/download) and click on the Download button.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/2d3dcf8d-3348-4efb-ab07-89fdd8532872)

2. Then, in the terminal run this.

```bash
bash Anaconda3-2023.09-0-Linux-x86_64.sh
```

3. You will be asked to press Enter to install it, and then the Usage Agreement will appear, press Enter until it ends. And for every question made during the installation process accept it.

4. Once it is done, you will see that your terminal looks like this.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/548be4d0-56c0-44a3-b8ae-c1590f67a1e5)

5. The *(base)* at the beginning of my username means that we are working in the *base virtual environment*. To create another, you have to type this.

```bash
conda create -n {virtual Environment name} {python version if neededd}
```

An example is shown below.

```bash
conda create -n my_py3_env python=3.8
```

6. Then your new virtual environment will be created, and probably the *(base)* at the beginning will change to your virtual environment name. For future activation and deactivation of the virtual environments, run this commands.

To activate any virtual environment:

```bash
conda activate {Vritual Environment name}
```

To deactivate any virtual environment:

```bash
conda deactivate
```

Finally, in your ```/home/{username} ``` directory you will see that a new folder appeared with a name related to *anaconda*. Inside that folder, there are many others, the one with the name *envs* will contain the virtual environments you will create.

## Installing required libraries in the virtual environments

To install any library you must run this command.

```bash
conda install {Name of the Python package}
```

For example:

```bash
conda install future
```

You can also use pip2 or pip3 inside conda virtual environments. The following example lets you install CARLA python API, so you must run it. 

```bash
pip3 install /home/{username}/carla/PythonAPI/carla/dist/{name of the python API}.whl
```

Finally, to have all the libraries to run some CARLA examples you will have to run this commands in the Terminal. 

```bash
conda install future
```

```bash
conda install numpy
```

```bash
conda install matplotlib
```

```bash
conda install open3d
```

```bash
conda install pillow
```

To install pygame, you have to run this 2 commands. 

```bash
conda config --append channels conda-forge
```

```bash
conda install pygame
```

And also run this as well. 

```bash
sudo apt-get update &&
sudo apt-get install wget software-properties-common &&
sudo add-apt-repository ppa:ubuntu-toolchain-r/test &&
wget -O - https://apt.llvm.org/llvm-snapshot.gpg.key|sudo apt-key add
```

To see what packages your conda virtual environment has, type ``` conda list ```, you will see the carla package after this. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/baffc291-c7b4-43bf-a4f5-41fb4ec72267)

Finally, do not forget to deactivate the virtual environment you are using, once you are done with it. 

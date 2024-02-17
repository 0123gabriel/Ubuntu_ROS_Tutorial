# Tutorial to install CARLA 0.9.15 version to work with Pyhton 2.7.17 in Ubuntu 18.04

To install CARLA you have 2 methods, this one is to use CARLA maps and vehicles that come with the installation. If you want to create your own maps or use your own vehicles, you will need to watch the other tutorial.

For documentation you can visit CARLA website (https://carla.readthedocs.io/en/latest/). 

## Requirements
- **System requirements:** CARLA is built for Windows and Linux systems.
- **An adequate GPU:** CARLA aims for realistic simulations, so the server needs at least a 6 GB GPU although we would recommend 8 GB. A dedicated GPU is highly recommended for machine learning.
- **Disk space:** CARLA will use about 20 GB of space.
- **Python:** Python is the main scripting language in CARLA. CARLA supports Python 2.7 and Python 3 on Linux, and Python 3 on Windows.
- **Pip:** Some installation methods of the CARLA client library require pip or pip3 (depending on your Python version) version 20.3 or higher.
- **Two TCP ports and good internet connection:** 2000 and 2001 by default. Make sure that these ports are not blocked by firewalls or any other applications.
- **Other requirements:** CARLA requires some Python dependencies. Their installation will be shown later on this tutorial.

It is important to mention that CARLA website has instructions to install CARLA simulator but some commands are not currently working. That is why, after some research, I have found the following GitHub forum with a solution given by nenadilic84 (https://github.com/carla-simulator/carla/issues/7017). The steps he mention are the following:

**1. Install Required System Dependency:** Run the following command in the Terminal.
```bash
sudo apt-get -y install libomp5
```
**2. Download the CARLA 0.9.15 Release:** Download the CARLA_0.9.15.tar.gz file (approximately 16GB) from the official release.
```bash
wget https://carla-releases.s3.us-east-005.backblazeb2.com/Linux/CARLA_0.9.15.tar.gz
```
**3. Unpack CARLA:** You have to create this directory path: /opt/carla-simulator/. To do that you have to run the following command.
```bash
sudo mkdir -p /opt/carla-simulator/
```
Then run this command:
```bash
sudo tar -xzvf CARLA_0.9.15.tar.gz -C /opt/carla-simulator/
```
**4. Install the CARLA Python Module:** Install the CARLA Python module.
```bash
python -m pip install carla==0.9.15
```
# (Optional) Install Visual Studio Code to see some example codes with CARLA
You have to run the following command line.
```bash
sudo snap install code --classic
```
Once you have Visual Studio Code, you are able to watch the examples codes that came during CARLA installation. To watch them, you have to run the following instructions in the Terminal.

```bash
cd /opt/carla-simulator/pythonAPI/examples/
code {file name}.py
```

Visual Studio Code should open, and you will see that python need some dependancies. Ton install those extra libraries, you have to run the following command in the Terminal.

```bash
pip install --user future numpy pygame matplotlib Pillow
```
The most important libraries are numpy and pygame (they are recommended to instal by CARLA website), but you will need the rest of them to run different codes. 

## Running CARLA with NVidia Drivers

If you don not have NVidia GPUs, please read the next section. 

As it was mentioned before, you will need a GPU with at least 6GB. CARLA versions after 0.9.12 work with Vulkan Drivers, which are from NVidia. So if you have those type of GPU, you will be able to run the following instructions.

```bash
cd /opt/carla-simulator/
./CarlaUE4.sh
```

If your GPU does not have the minimum memory, you might need to run CARLA with low quality graphics, to do that, please run this command.

```bash
./CarlaUE4.sh -quality-level=Low
```
Once that was executed, you will see the following window.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/5795fb3d-9e61-4d17-804c-cb67dc20efbb)


If you want to spawn vehicles and people, you have to open a new Terminal, and run this instruction.

```bash
cd /opt/carla-simulator/PythonAPI/examples/
python generate_traffic.py
```

And you some vehicles and people will appear. You can also will be able to see some graphics about vehicle data as friction, steering values, etc. 

![WhatsApp Image 2024-02-07 at 20 32 26_962933ee](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/9ea0b18e-191d-4e79-a9e2-0a0df7bea269)


Finally, if you want to try drive a vehicle with CARLA and see how it works and what options does it have, you can open a new Terminal, and run this.

```bash
cd /opt/carla-simulator/PythonAPI/examples/
python manual_control.py
```
After that, you will see the controls in your Terminal

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/6d776da1-6bbc-4174-af0b-3d7079a45137)

And a windows like this one will pop up. 

![Screenshot from 2024-02-06 19-50-30](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/6a6028dc-941b-4e09-a237-f3be64ece37a)

## Runing CARLA without NVidia Drivers

As it was mentioned before, CARLA versions after 0.9.12 work with Vulkan Drivers, so you may have some problems trying to run it without them. However, here is how you can do it. 

If you do not have Vulkan Drivers, you should have OpenGL dirvers, which were used before NVidia started making their GPUs. You can check those drivers running the following in the Terminal. 

```bash
glxinfo | grep "OpenGL version"
```

This CARLA version will not work without Vulkan Drivers. You can try but a pop up window will appear and will say that CARLA could not found the needed drivers. To solve that problem, run this in the Terminal. 

```bash
sudo apt-get install libvulkan1 libvulkan1:i386 mesa-vulkan-drivers mesa-vulkan-drivers:i386
```

Once you did that, your computer will have Vulkan Drivers and you are now able to run CARLA. It is important for you to know that having wrong drivers may give you some problems. 

## CARLA client library

This libraries are used to enable the comunication between CARLA and a DRL algorithm to probe them. You will find this library in the following path.

```bash
cd /opt/carla-simulator/PythonAPI/carla/dist/
```

To see them, type "ls" in the terminal. You will that there is 4 files: 2 ```bash .egg ``` files and 2 ```bash .whl ```. These are the compressed form of the libraries we need.  

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/9ae81e8b-9e58-4ae6-8a5e-07b6e4f30bb0)

As we are using CARLA 0.9.15, we need to install .whl files, beacuse .egg files are used by CARLA versions prios 0.9.12. 
Now, to install the library needed, you have to know which python version you will use to develop de DRL algorithm. If you are using python 2, you have to install the .whl file that contains cp27 in the name, and, of course, if you will use python 3, you have to install the other file. 

To install that file, I highly recommend to do it in a virtual environment to avoid any future conflict. To make a virtual environment, you have to create a new folder where the virtual environment will stay. Once you have created, please right click anywhere in the folder, and select Open in Terminal. In the Terminal, run 

```bash
pip install virtualenv
virtualenv -p /usr/bin/python2.7 {Name of the virtual environment}
source {virtual environment name}/bin/activate
```

This will starts the virtual enviroment and to know that you are actually working on the virtual environment, your Terminal will be shown like this.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/81fb3e03-3635-4b1a-a809-a033622525d7)

If you try to run any Python code there, you will have some errors saying that you do not have the required libraries. That is why all libraries we have installed until this point can not be recognized inside the virtual enviroment, so you will to install them again in the virtual Environment. 

Finally, once you have finished using the virtual environment, do not forget to close it. To do that, run the following line. 

```bash
deactivate
```

Keep going with the .whl file installation. Once you are in the virtual environment you already made, run this line in the Terminal.

```bash
pip install /opt/carla-simulator/PythonAPI/carla/dist/carla-0.9.15-cp27-cp27mu-manylinux_2_27_x86_64.whl
```

And you are done with CARLA installation

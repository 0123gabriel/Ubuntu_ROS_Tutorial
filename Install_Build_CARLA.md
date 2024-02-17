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

* ***130 GB disk space:*** CARLA will take aorund 30GB and Unreal Engine around 91GB, so you will need 130GB approximately taking into account extra programs to use this simulator software. To check your disk free-space, runt his command.

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

If when you run the previous command, you get a message saying that Ubuntu do not recognizes that command, and recommend you to instal net-tools, do it by this command. 

```bash
sudo apt-get install net-tools
```

### Software requirements

* ***Python:*** You will need to have python2 and python3 installed in your computer. Most of the Ubuntu OS come with python3, and you can check that by running this command

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

If you already have pip, please upgrade it and to do that read the third command show below. But, if you do not have it, run this to install **pip**. You might be asked to type *Y* to install it, please do it and press enter. 

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

If you already have pip3, upgrade it by running the third command show below. If you do not have it, to install ***pip3*** run this. You might be asked to type *Y* to install it, please do it and press enter. 

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

* ***CARLA software required:*** CARLA requires some prevoius software installed in your computer. To have them, copy all of the below commands at once, and paste them in the terminal, then press enter. 

```bash
sudo apt-get update &&
sudo apt-get install wget software-properties-common &&
sudo add-apt-repository ppa:ubuntu-toolchain-r/test &&
wget -O - https://apt.llvm.org/llvm-snapshot.gpg.key|sudo apt-key add
```



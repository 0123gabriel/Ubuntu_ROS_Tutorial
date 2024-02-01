# Tutorial to install CARLA 0.9.15 version to work with Pyhton 2 in Ubuntu 18.04

For docuemntation you can visit CARLA website (https://carla.readthedocs.io/en/latest/). 

## Requirements
- **System requirements:** CARLA is built for Windows and Linux systems.
- **An adequate GPU:** CARLA aims for realistic simulations, so the server needs at least a 6 GB GPU although we would recommend 8 GB. A dedicated GPU is highly recommended for machine learning.
- **Disk space:** CARLA will use about 20 GB of space.
- **Python:** Python is the main scripting language in CARLA. CARLA supports Python 2.7 and Python 3 on Linux, and Python 3 on Windows.
- **Pip:** Some installation methods of the CARLA client library require pip or pip3 (depending on your Python version) version 20.3 or higher.
- **Two TCP ports and good internet connection:** 2000 and 2001 by default. Make sure that these ports are not blocked by firewalls or any other applications.
- **Other requirements:** CARLA requires some Python dependencies. Install the following dependencies.

```bash
pip install --user pygame numpy
```

It is important to mention that CARLA website has some instructions to install CARLA simulator but some commands are not currently working. That is why, after some research, I have found the following GitHub forum with an answer given by nenadilic84 (https://github.com/carla-simulator/carla/issues/7017). The steps he mentioned are the following:

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

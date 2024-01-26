# Installing Ubuntu 18.04 version and ROS Melodic

## Create a bootable Ubuntu USB
1. Click in the given link, then scroll down until the "Past releases and other flavours" section. Right there you will click on 18.04 version. Finally, download the Desktop Image file and remember the location of it. 
https://ubuntu.com/download/alternative-downloads
2. Download Rufus, a free and open source USB stick writing tool. (https://rufus.ie/)
3. Launch rufus and set like any of the images below. Then click on the START button and the download of the ISO file on the USB will begin. (Note: The difference between the two images is in the Partition Scheme, you should use MBR if your computer was made before 2010, otherwise, you should use GPT).

![image](https://github.com/nabihandres/COOP_tutorials/assets/108648272/89aa84a6-6d8d-451e-aa93-6c72e06750a3)
![image](https://github.com/nabihandres/COOP_tutorials/assets/108648272/7f5820c3-c36b-4e42-9c8f-8913e0cbfa57)

## Make a partition for Ubuntu

1. Open the command prompt (cmd) and type diskmgmt.msc
2. Choose the storage in the Volume Column that will be used to make the partition to store Ubuntu OS and right click on it, then press Shrink Volume button.

![image](https://github.com/nabihandres/COOP_tutorials/assets/108648272/956ce598-ac76-4d38-8d21-098b2da3f045)

3. Assign the appropriate amount of storage for Ubuntu. Ubuntu's page recommend at least 25GB, and you also should think about the programs you will use in that OS.
4. Click on the Shrink button.

![image](https://github.com/nabihandres/COOP_tutorials/assets/108648272/04456856-4302-4b49-939c-71cc0026ec57)

5. After that, you can check the partition was made, and it does not have any number, and it is unallocated.

![image](https://github.com/nabihandres/COOP_tutorials/assets/108648272/5a0a0dce-5b34-41fc-b859-cfb4796c5acf)

## Install Ubuntu

1. You will have to restart or reboot your PC or laptop with the USB with Ubuntu ISO plugged in.
2. Once your computer is getting started, you need to press F12 to access to the BIOS. If your computer does not access to the BIOS with F12, please look for the correct button needed to be pressed.
3. When BIOS is open, in the left hand section, you will see the bootable devices that the computer recognize. Please select the USB.
4. Ubuntu will boot, and you will see an icon that says "Install Ubuntu", select that button.
5. After that, you have to set some feauters of the system such as the language. The following images show those easy steps. Note: It is recommended to click the Normal Installation option. 
6. After select the Normal installation, it will ask you the Installation Type, you have to select the option "Something else" which allows you to use the previous made partition.

 ![image](https://github.com/nabihandres/COOP_tutorials/assets/108648272/7b428f2a-faef-4e39-8fec-9f1bd917e3e7)
 ![image](https://github.com/nabihandres/COOP_tutorials/assets/108648272/39f8488c-4d70-40c2-a2dd-697ab4590663)
 ![image](https://github.com/nabihandres/COOP_tutorials/assets/108648272/60e522ef-39a2-4e80-8a91-0e25857af08c)
 ![image](https://github.com/nabihandres/COOP_tutorials/assets/108648272/4f492d9a-614e-41e5-9d9b-73fe0343f062)
 ![image](https://github.com/nabihandres/COOP_tutorials/assets/108648272/d500b291-e718-4139-9322-49d01a1cd6af)

7. In the displayed list, look for the the "empty space" or "free space". You will know which one you should select based on the size of the partition you made, because it will have an approx size of the partition made.
8. Then, click on the ‘+’ button under the list.

![image](https://github.com/nabihandres/COOP_tutorials/assets/108648272/324006e9-0fe5-4d1d-92ec-506a2cd995c7)

9. A pop up window will apper, do not change the size, select the option "logical", and the option "The point where this space starts", and in the last one, look for the "/" option in the desplegable list.
10. Then click on the Okay button, and that pop up window will close.
11. Select the storage you just made, then select the Install now button, and click on Continue in the pop up window. 

![image](https://github.com/nabihandres/COOP_tutorials/assets/108648272/15d7052f-0290-4cc3-9fe6-b40c3906c357)
![image](https://github.com/nabihandres/COOP_tutorials/assets/108648272/44e64665-8e57-4628-9c6e-13e56b46daa2)

12. You will need to select your country and time zone, and complete the blank spaces. After that, click on Continue and Ubuntu will installed.
13. Finally, restart your PC.

![image](https://github.com/nabihandres/COOP_tutorials/assets/108648272/c73d0504-c1fd-4479-95b1-e7c1b463dc31)
![image](https://github.com/nabihandres/COOP_tutorials/assets/108648272/e1a7020b-c3f4-4faa-8d28-a985665d1a51)
![image](https://github.com/nabihandres/COOP_tutorials/assets/108648272/85f9c9d7-a6ff-4b8d-9dfb-e14e7fd383d2)
![image](https://github.com/nabihandres/COOP_tutorials/assets/108648272/8ed751a0-ef61-40cb-8d5a-b27586ae1b77)

14. From now on, every time you turn your laptop on, you will be asked about the OS you will use.
15. Before install ROS Melodic, be sure you have internet access in your Ubuntu OS.

## Install ROS Melodic

1. Open the terminal. You can do that clicking on the square made of 9 points in the left-bottom corner, and searching the "Terminal" word.
2. Copy one at a time the given commands.

    sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
    sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654
    sudo apt update
    sudo apt install ros-melodic-desktop-full
    echo "source /opt/ros/melodic/setup.bash" >> ~/.bashrc source ~/.bashrc
    sudo apt-get install python-rosinstall python-rosinstall-generator python-wstool build-essential
    sudo apt-get install python-pip
    sudo pip install -U rosdep
    sudo rosdep init
    rosdep update

## Important programs that you may need to download

  1. terminator (https://shanepark.tistory.com/313)

    sudo apt-get install terminator
    
  2. sublime text (https://jjeongil.tistory.com/1346)

    sudo apt update
    sudo apt install apt-transport-https ca-certificates curl software-properties-common
    curl -fsSL https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -
    sudo add-apt-repository "deb https://download.sublimetext.com/ apt/stable/"
    sudo apt update
    sudo apt install sublime-text
    
  3. screen recorder (https://pinkwink.kr/913)

    sudo add-apt-repository ppa:maarten-baert/simplescreenrecorder
    sudo apt-get update

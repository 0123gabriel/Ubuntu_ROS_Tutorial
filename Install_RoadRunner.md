# Tutorial to install MathWorks RoadRunner on Ubuntu 20.04

I consider important to bementioned that RoadRunner cannot be executed in Ubuntu 22.04, so I had to install virtual machine with Ubuntu 20.04.

1. Go to MathWorks website and sign in (https://www.mathworks.com/login).
2. Then open the following link to request your RoadRunner license (https://la.mathworks.com/academia/student-competitions/carla-autonomous-driving-challenge.html).
3. Once you are there, click on the Request Software button.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/e8bb554e-6694-4d78-950c-55db3d82117c)

4. A pop-up windows will apper, and click on the Request Software Form button.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/8e980e08-cc63-4228-9840-2cbbdcbb7c26)

5. Fill out all the blank spaces, and check the two boxes: the first one about "Team Leader/Faculty Advisor Confirmation" and the other one to agree the Use Agreement. The first three blank spaces should be filled out with your MathWorks information account. Finally click on submit and MathWorks Team will check your Software Request and they will send you an activation key to your email after about 2 days. 
 
![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/a8ee2ae8-86c1-4259-96e8-743d6ed6ed49)

6. Once you get the email with the activation key, go to the following website (https://www.mathworks.com/licensecenter/licenses) and click on the 2023 CARLA Autonomous Driving Leaderboard. Click on the Link License button in the upper right corner and register the license number/activation key you received in the mail to link your license. Once the license connection is successful, you will see your new RoadRunner license on the license selection screen.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/aba49ba8-4a65-4093-aac5-f664d2660fc2)

Or in yout account, after loggin in. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/f14b29f1-7c58-4395-9055-8cbf07269fd6)

7. Click on the RoadRunner lisense, then on the Install and Actibe tab, and finally in the Active a Computer Button.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/025acb81-442a-4da0-8495-24fc96c3168f)

8. Fill out the blanks with your computer information. In this case, we are installing RoadRunner in Ubuntu, the we have to select Linux in the Operative System field.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/a010dfd4-e165-4da3-b94e-a40f6c9fc42b)

9. To check your computer Host ID you can do it with 2 methods:

### ***1st Method***

You have to run the following commands in the terminal.

```bash
sudo apt install net-tools
netstat -i
```

The output of that command will show a table, you have to look to the Iface column which shows the net interfaces your computer has. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/7c10c7bf-6ebd-4453-9f1c-85fcc6e6822f)

To know your Host ID run the following command in the terminal

```bash
/sbin/ifconfig {name of the net interface}
```

In this case, you shoul run this

```bash
/sbin/ifconfig enp56s0
```

Run that command for every Iface your computer showed. The output of those commands will the Host ID which is the 12 digit number next to the "ether" word. In my case, my computer showed three names in the Iface column, so I had to try the previous command three times, and I found out that my computer has a Ethernet and Wi-Fi net interfaces, so I have 2 Host ID. 

### ***2nd Method***

Run the following command in ther terminal

```bash
ifconfig
```

This will show all the information about every net interface, so you will watch the same information with the previous method, with less steps. It is important to mention that the interfaces that star with "en" are mostly related with Ethernet interfaces, and if it starts with "w" is mostly realted to Wi-Fi interfaces. 

10. Copy the Host ID you will use. In this case, I am going to use my Wi-Fi net interface so I selected my Host ID related to wlo1 interface.
11. Set a name for your computer, to know which machine is using RoadRunner when you launch it, and then click on Continue.
12. A window will ask you if the software is installed, clik on the answer No, and click on Continue.
13. MathWorks will ask you to download or email you the License File, you can do both if you want, and click on the intructions link, to read more about the installation process.
14. Go to the following link (https://www.mathworks.com/downloads/web_downloads) and click on Get RoadRunner Products desplegable, and download it by clicking on the blue button, which should has written the Operative System you have, and previously selected.

## Installing RoadRunner

If you are working in Ubuntu 16.04, 18.04, or 20.04, you just need to click on the .deb file that was downloaded previously, and then click on the green Install button. The following window will appear. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/46733497-76e2-4384-8519-acdd0e5a2aee)

Then, click on Next button, and select the path where your license.lic file is. It should be in the Dowmloads folder.   

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/ff78bae2-81d6-4c2e-9cac-a9573ecbb151)

After that, you will have RoadRunner running correctly, and it should look like this. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/791ca4fe-0855-4a97-8e53-955617bae588)

# Creating a road 

1. Click on New Project, and the give a name for the project, select the location of it, and check the boxes you want.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/69014a68-ecb7-4d0e-abdd-e94e83c03726)

2. Click on Create, and then click on New Scene

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/3abbb311-d276-4f28-ad98-9a832019cd9a)

3. This window will open.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/c4f76c3f-135f-4a9b-9c9f-f04f2b6684de)

4. To create a road, RoadRunner has the Road Plan Tool option activated, so you can right click in any part of the grid, and the a red dot will appear. You can set the dot coordinates to be more accurate.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/d52e6dd2-8145-406c-8fb2-06a0036f53ab)
 
5. Then, right click in any other point, and you will also able to set the coordinates of the second point.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/7a86af04-1185-4d76-a8ac-5760d226c021)

6. 









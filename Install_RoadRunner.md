# Tutorial to install MathWorks RoadRunner on Ubuntu 16.04, 18.04 and 20.04

I consider important to be mentioned that RoadRunner cannot be executed in Ubuntu 22.04 (I tried soo many things, and anyone worked out), so I had to install a virtual machine with Ubuntu 20.04, but you can also try with Ubuntu 16.04 or 18.04.

1. Go to MathWorks website and sign in (https://www.mathworks.com/login).
2. Then open the following link to request your RoadRunner license (https://la.mathworks.com/academia/student-competitions/carla-autonomous-driving-challenge.html).
3. Once you are there, click on the Request Software button.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/e8bb554e-6694-4d78-950c-55db3d82117c)

4. A pop-up windows will appear, and click on the Request Software Form button.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/8e980e08-cc63-4228-9840-2cbbdcbb7c26)

5. Fill out all the blank spaces, and check the two boxes: the first one about "Team Leader/Faculty Advisor Confirmation" and the other one to agree the Use Agreement. The first three blank spaces should be filled out with your MathWorks account information. Finally click on submit and MathWorks Team will check your Software Request and they will send you an activation key to your email about 2 days later. 
 
![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/a8ee2ae8-86c1-4259-96e8-743d6ed6ed49)

6. Once you get the email with the activation key, go to the following website (https://www.mathworks.com/licensecenter/licenses) and click on the 2023 CARLA Autonomous Driving Leaderboard. Click on the Link License button in the upper right corner and register the license number/activation key you received in the mail to link your license. Once the license connection is successful, you will see your new RoadRunner license on the license selection screen.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/aba49ba8-4a65-4093-aac5-f664d2660fc2)

Or in yout account, after loggin in. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/f14b29f1-7c58-4395-9055-8cbf07269fd6)

7. Click on the RoadRunner lisense, then on the Install and Actibe tab, and finally in the Active a Computer button.

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

In this case, you should run this

```bash
/sbin/ifconfig enp56s0
```

Run that command for every Iface showed. The output of those commands will show the Host ID which is the 12 digit number next to the "ether" word. In my case, my computer showed three names in the Iface column, so I had to try the previous command three times, and I found out that my computer has an Ethernet and Wi-Fi net interfaces, so I have 2 Host ID. 

### ***2nd Method***

Run the following command in ther terminal

```bash
ifconfig
```

This will show all the information about every net interface, so you will watch the same information with the previous method, with less steps. It is important to mention that the interfaces that star with "en" are mostly related with Ethernet interfaces, and if it starts with "w" is mostly related to Wi-Fi interfaces. 

Then, going back to fill out the Host ID field,

10. Copy the Host ID you will use. In this case, I am going to use my Wi-Fi net interface so I selected my Host ID related to wlo1 interface, but anyone can work out.
11. Set a name for your computer to know which machine is using RoadRunner when you launch it, and then click on Continue.
12. A window will ask you if the software is installed, clik on the answer No, and click on Continue.
13. MathWorks will ask you to download or email you the License File, you can do both if you want, and click on the intructions link, to read more about the installation process.
14. Go to the following link (https://www.mathworks.com/downloads/web_downloads) and click on Get RoadRunner Products desplegable, and download it by clicking on the blue button, which should has written the Operative System you have, and previously selected.

## Installing RoadRunner

You just need to click on the .deb file that was downloaded previously, and then click on the green Install button. The following window will appear. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/46733497-76e2-4384-8519-acdd0e5a2aee)

Then, click on Next button, and select the path where your license.lic file is. It should be in the Dowmloads folder.   

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/ff78bae2-81d6-4c2e-9cac-a9573ecbb151)

After that, you will have RoadRunner running correctly, and it should look like this. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/791ca4fe-0855-4a97-8e53-955617bae588)

# Creating a road 

This section explains a reduced number of tools RoadRunner has, if you are interested in try differente tools, you can check the RoadRunner website (https://la.mathworks.com/solutions/automated-driving/roadrunner-tutorial.html) (this one a more advanced https://la.mathworks.com/videos/series/getting-started-with-roadrunner.html)

1. Click on New Project, and then give a name for the project, select the location of it, and check the boxes you want.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/69014a68-ecb7-4d0e-abdd-e94e83c03726)

2. Click on Create, and then click on New Scene

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/3abbb311-d276-4f28-ad98-9a832019cd9a)

3. This window will open.  

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/c4f76c3f-135f-4a9b-9c9f-f04f2b6684de)

Let's understand some general parts of the application. In the bottom left side, you will see the 2D Editor | Profile section; this tool represents in 2D the road you have made or selected, and any inclination in it will be the slope that lane has. For example, in a flat and straight lane, you will see a line representing the road, you can give to this line some downwards and upwards slope by dragging the end points, and if you check that zone and see some points in the middle of the line, they will let you bend the road.  

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/7104e3fd-c93a-4fc3-a373-422744eaae08)

Next to the last section, you will see the Library Browser which have features you can give to the lanes as the material of the road, some signs, etc. In the right side you will see a black box which has the title Atributes, in this part should appear some aspects you can modify like the distance, some coordinates, etc. Then in the top part, there are the needed tools to create and modify the lanes; in the left side you will see three tools, they let you to rotate, and select the axis of one road, and finallly, in the center of the app you have a grid where you can draw your road, and in the top and bottom right corners you have some tools to change the view of the grid. Now, let's continue creating a new road, so select all the road by clicking and dragging the mouse, and the press Delete. 

4. To create a road, RoadRunner has the Road Plan Tool option activated, so you can just right click in any part of the grid, and a red dot will appear. You can set the dot coordinates to be more accurate.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/d52e6dd2-8145-406c-8fb2-06a0036f53ab)
 
5. Then, right click in any other point, and you will also able to set the coordinates of the second point.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/7a86af04-1185-4d76-a8ac-5760d226c021)

6. After that, you need to delete the lane that is going leftwards, to do that click on the Lane Add Tool, click on the lane, and by clicking and dragging create a box that selects all the leftwards lane, and the press Delete.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/338cfdb0-a5aa-4ff4-a9e6-d8ebac0c5c0a)

You will see that when you move the mouse over the lane, some blue lines appear, they let you to repeat some features the road has like the bike lane, etc. 

7. With the process of the sixth step, delete the light gray part of the road.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/18a65106-d543-4505-a625-1546c0dc20c8)

You should end with something like this. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/fba1382f-17b4-46a7-b3ab-43ff79e5caea)

8. The we will change the appearance of the road, so to delete the yellow lines click on the Lane Marking Tool, and select (following the same process of dragging) the yellow lines, and then delete them. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/9d989597-d0f2-4a1c-a0de-70aa3981243c)

You should get something like this.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/02748f51-567e-446d-b8c4-a350f1c2b7b6)

9. Now, let's widen the road by clicking the Lane Witdth Tool. Select the road, and in the right side type the desired width, in this case, I typed 8 meters.

 ![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/67c707c0-86ac-4fea-bb41-37e1cf676378)

 10. To chose the directions of the road, you can select the Lane Tool, then click on the lane. After that, in the right side you see some option, and in the Travel Direction field, select Forward. That will create some arrows going rightwards.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/3540a65a-4832-4363-ba1f-ff925aaa81c5)

11. To extend the road, you have to select the Road Plan Tool, and click on the end of the road you want to extend, and then click on an empty space where the road ends.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/cad4f37a-0db8-4084-acb1-183d84a2a38d)

In the last image, I created a circular corner by right clicking in a point far from the end of the previous lane, and to add more points to modify your lane, you can right click on the blue lines, and to give to the road the desired form, move those points and see what happen, and also you can use the 2D Editor | Profile, this could also help given some slope to the road. At this point, I had to save the scene, so you can click on File tab, then Save As, and select the location of the scene (I would recommend to save it in the place that the app has by default). When you want to continue working in, you have to open RoadRunner and your scene will be showed in the Recent Files section, so you can just click on it and keep working. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/5cf9b44e-c910-407f-94af-690d15fe548b)


12. Keep playing with the reviewed tools, and create a closed-loop road. When it is done, you will see that the space inside the road will be filled with a green ground. I have created this one, which is mostly flat, but has some slope which is showed below. 
 
![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/63741599-39e4-4134-8e63-09e184f43999)

13. To add some ground around and out the road, you can select the Surface Tool. Then, right click and create a closed loop, and after that, the section will be filled with a green color. This step is not mandatory, but it can get to the road some visual interest.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/1fb4abc4-f267-4a8c-888e-57dd044995a3)
 
14. Then, select the World Setting Tool and be sure that all the map is bunded by the blue lines, and click on Apply World Changes. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/06673a45-c7a5-4a22-9b45-3a5331c22e71)

15. You can also set the Latitud and Longitude of the map.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/35badd56-a584-499e-b5c6-895ab7d2aec6)

You should end with something like this. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/540e20b7-74bd-4989-a1ed-eb519e8eb3bb)

16. When you have finished creating your custom map, click file from the top menu, then click on Export, and select CARLA firmbox.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/581f8e12-deb4-429d-b8f8-7d2d24e67b68)

17. In the window that pops up, check the following options:

    * **Split by Segmentation:** Divides the mesh by semantic segmentation.
    * **Power of Two Texture Dimensions:** Improves performance.
    * **Embed Textures:** Ensures textures are embedded in the mesh.
    * **Export to Tiles:** Choose the size of the tile or leave unchecked for only one piece.

    And leave unchecked:
    
    * **Export Individual Tiles:** Generates one ``` .fbx ``` file with all map pieces.

    And leave the values that are by default in the fileds of Tile Size and Tile Center. Then click on Export, and watch the path where it is saved.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/55f16aeb-22d9-4ae6-99be-6c0d0b2498c1)

18. If you get this errors, do not worry about them, they are related to some assets, but we are not using them. The important part is the path where the files were exported, you can checked them in the line that begins with Exported, but they should be inside the Exports folder which is inside the folder that contains all the project. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/af9f4363-4625-4472-a3f1-01b6d155790f)

20. Go to path where you exported the files of the map, and make you sure that the ``` .xodr ``` and the ``` .fbx ``` files have the same name.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/d383063d-8d6b-4519-baa2-cf102d21195b)

## Applying a custom map to the CARLA simulator

1. Go to the Import folder which is inside the CARLA folder that was created when we installed it.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/fd7a4563-b38b-4163-90af-d507d5f7fb58)

2. Delete the README.md file. If you open it, you will read that is says that in this folder you sould put the map file that we already created. It is important to mention that if there is any other file in that folder, the custom map will not be applied.
3. Save the ``` .fbx ``` or ``` .xodr ``` file in the Import folder.
4. Open a terminal, then change the directory to CARLA folder, and run this command. This may take some minutes.

```bash
make import
```

5. Run CARLA simulator using this command in the same CARLA folder directory.

```bash
make launch
```

6. In th bottom part, you will see the Content Browser.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/6b67d12c-89af-4034-a381-4c8840cbe9f5)

Click on CARLA folder

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/d9bcff31-4ce6-43fc-ad0e-089fabec252d)

7. Then click on Maps folder, and create a new folder by right clicking anywhere. This folder will have your customed map. y folder is called carlaRoad.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/59179e81-b2c3-46b9-8fda-08e44abc0464)

8. Then open the new folder you just created. After that, under the Content Browser title, you will see a Add/Import green button, and under it, a Filters button. In the left side of the Filters button, there is another button with a small triangulo in it, and some horizontal lines. Click that one, and a kind of folder browser will appear. Then, in the same directory of your folders, click on the BaseMap Folder.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/0dad7131-3042-44cd-8ae6-7c05c2725da0)

19. In the BaseMap folder you will see that there is an orange file, they are called "level". Click and drag it to the folder we just created. You will see that once we are dragging the file, a box appear and says "Move or copy BaseMap". And then, another box will appear asking if you want to move or capy that file, please select "Copy Here". Finally, the folder you created will look like this.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/1298c0b4-4123-4b78-9895-a1e424d74078)

20. You can rename that file (I named as carla_road), but we need it becuase it has some basic parameters about the illumination of the map. If we do not use it, we will get a completely dark map, and it will be unuseful.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/37d09419-ff5c-48f4-bfdd-8a88bc9ac9d1)

21. Then, click on the Add/Import green button, and then in Import Asset

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/89531a14-5db3-48e5-9164-ec459b708d39)

22. Browse your ``` .fbx ``` file and open it.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/26a53d02-d9e9-42d3-b16c-d4f341ac3b47)

23. A pop-up window will appear, and make sure to uncheck the following options:

* Auto Generate Collision
* Combine Meshes
* Force Front xAxis
* Normal Import Method - Import Normals

And check the following options:

* Convert Scene Unit
* If you want to import materials and textures:
    * Material Import Method - Create new materials
    * Import Textures

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/a8e05a0b-cf90-4434-bd87-1247b8b64f76)

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/6041a8b7-662f-4bef-821c-741c85ca42a1)

24. Double click on the level file, and your map will open. If a window like the one below pops up, click on Save Selected. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/4b8f795e-6833-4184-9d97-8357f4edb2e2)

You should have something like this. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/5fef7c4b-0ee4-4aff-aa84-e9262229b4bc)

25. Once everything is loaded up, you should end with several Static Meshes in the folder you have selected. Select all of them, and dragg those into the level which is already open.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/d83b68b6-06a2-4bb9-8df8-01c91c147297)

26. In the left section, you have the World Outliner, and under that one the Details section, and inside of it, the Tranform section where you have to set the location with zeros. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/d4e050da-e3ac-464a-9500-d9819cabff27)

27. Now, we have to set the users perspective at the start of the simulation. In the Place Actors menu on the left, click on the Player Start actor and move it to the location where the user's perspective will start. You can use the on-screen XYZ arrows to position it or change the Location and Rotation values in Details -> Transform on the right to adjust the position.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/94c08fba-d089-49e4-a335-50d2afe0318d)

28. This step will show you how to set that map as the default map. In case you do not want it to be the default map, you will have to go to the path with your level file and custom map, and open it manually. But if you want to have this open when you run Unreal Engine go to Settings (which is in the same bar where Play button is) and select Project Settings... option.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/34a33101-98c3-403e-8a68-f5c65b51ca3d)

29. In the sidebar, in the Projects section, click on Maps & Modes. Then in right side section, look for the Editor Startup Map, click on the downwards arrow, and search your map. Here you will also see that there are more maps that came with the CARLA installation.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/6550de98-2fda-4ac8-8e4b-57cdba5e4864)

You can relaunch Unreal Engine to see that your map is now the default one. 

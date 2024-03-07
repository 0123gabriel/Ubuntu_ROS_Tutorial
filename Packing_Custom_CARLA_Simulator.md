# Packing a Customed CARLA Simulator

Packaging your project creates a distributable package for distributing your Unreal Game project to users. The overall process of packing consist in compile the project-specific source code, and then all the necessary content is converted or "cooked" into a format that can be used on the target platform. Next, the compiled code and cooked content are packaged together in a distributable package file, such as a Windows installer.

The advantages of creating a package for distribution versus running the CARLA simulator through the Unreal Editor include a faster and easier launch, the ability to distribute the CARLA simulator with custom vehicles and maps, and a smaller footprint. Packaging a project in CARLA Simulator involves the following steps.

1. Default game map configuration
2. Update map list
3. Other packaging options
4. Packaging

## 1. Default game map configuration

1. Run CARLA.
2. Click on Settings button at the top of Unreal Editor.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/40b81a50-b4bc-41df-b821-fdcec4ae1106)

3. Select Project Settings, and click on it.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/75c2131e-9f0b-4dcf-8240-a0988fc76a50)

4. In the window that pops up, in the left section, on the Project menu, select Maps & Modes.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/66f34aba-72f7-4892-bff9-872d7462d5c4)

5. In the Default Maps section click on the Show Advanced button.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/7726ad5c-61ae-4308-b145-13ca4ca7b277)

6. In the 4 fields that are in the Default Map section select your road file. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/64cbbbbb-0cf9-4271-ad58-ac3e4f3315cf)

## 2. Update map list

1. In the same window we opened in the previous step, in the Project menu, click on the Packaging option.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/31e2928d-1639-4af2-afaa-708b0e2cb21f)

2. In the Packaging menu (the first one), click on Show Advanced.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/b95d0755-7bbd-46d0-987d-1ef3ac1429b0)

3. In the new options that appear, search the "List of maps to include in a packaged build".

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/722f87d3-23c2-4c60-99da-9b03d6e642b5)

4. In that list, click on the '+' icon to add a new map. Then 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/93b2a631-8d21-4fed-adb2-dde7f5ee2d0d)

5. In the new blank space that appear at the end, type the directory where you have your map.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/c6198c74-ac72-43f4-9df8-2d357d00f8f0)

6. I would recommend to delete the rest of the maps, because building all unnecessary maps will significantly increase the packing time and capacity. You can delete them by clicking the inverted triangle icon on the right, and select the Delete button.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/286dc4d9-d87d-49db-a9c0-b3563964971b)

Once you have deleted all the maps except yours, you should get something like this.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/c6001360-9ab5-4330-b12c-9eb192ca39b4)

7. Go to the 'Additional Non-Assets Directories to Package' and remove all items except 'Carla/Config'.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/d65b9a2b-3594-45ed-8c4a-f3a3d449292a)

8. Minimize that window, and inside the directory where your custom map is create one folder called OpenDrive.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/84c05594-0cc8-441f-ab92-035961dc6f98)

9. Come back to the previous window and create another blank space in 'Additional Non-Assets Directories to Package' field by clicking on the '+' icon, and type the directory of the OpenDrive folder that we just create in the last step.

```bash
Content/Carla/Maps/{the name of the folder that contains your custom map}/OpenDrive
```

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/08250fe9-eb8f-4a8a-8372-590fa3b1a8df)

## 3. Other packaging options

1. In the same window we were working in the previous step, go to the Project menu.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/2281597d-57b6-43f8-966e-24f5e643ffda)

2. In the Build Configuration field set the Shipping option. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/25726a71-8ee2-4ad7-97d9-4ed7621eb90c)

## 4. Packaging

1. Close the Unreal Editor, and the open a Terminal, and go to the CARLA root directory, and run the following command.

```bash
make package
```

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/1a6f8fe4-c400-4f0b-9207-ff21a290f1c2)

2. 

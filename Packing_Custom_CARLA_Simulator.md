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

9. Come back to the previous window and create another blank space in 'Additional Non-Assets Directories to Package' field by clicking on the '+' icon, and type the directory of the OpenDrive folder that we just create in the last step. Do not include the Content folder beacuse CARLA include it by defult. 

```bash
Carla/Maps/{the name of the folder that contains your custom map}/OpenDrive
```

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/f5a8ebbb-4756-471d-93ee-5cc67933bb7d)

## 3. Other packaging options

1. In the same window we were working in the previous step, go to the Project menu.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/69c295c8-6b98-4c50-b6d6-bac88c85691d)

2. In the Build Configuration field set the Shipping option. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/59d6a8a1-82d5-47c6-8b91-c209d66bfc09)

## 4. Packaging

1. Close the Unreal Editor, and the open a Terminal, and go to the CARLA root directory, and run the following command.

```bash
make package
```

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/1a6f8fe4-c400-4f0b-9207-ff21a290f1c2)

Make sure that when that command ends its execution, you get something like the following message. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/1814a676-6a3a-40c5-8b9b-f7d33eecf570)

The second line shows where the CARLA released was created, and the thrid line that the process was completed correctly. 

Once the packaging is complete a CARLA simulator is created for distribution in the /Dist/CARLA-Shipping_(version) folder which in side the directory where the CARLA simulator is installed. If you want to distribute it, you can give out all files inside the /Dist/CARLA_Shipping_(version) folder. 

## Running the distribution package that was recently created

1. Go to the following directory using the Files app:

```bash
/{Carla root directory}/Dist/CARLA_shipping_{CARLA version}/LinuxNoEditor
```

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/0cf08a4f-07fe-4767-a77c-277fdec07a29)

2. Right click anywhere, and select Open in Terminal.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/d27a9568-055f-445f-b33b-6966e9d42b57)

3. Run the following command.

```bash
./CarlaUE4.sh
```

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/f1d499e9-7500-4c6a-9e88-85222fce829b)




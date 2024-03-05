# Using a customed vehicle with CARLA

This task will need 2 apps: the first one is Blender and the other one is an Add-on for Blender which let us configure the customed vehicle to be used in Unreal Engiene. This Add-on is called: Vehicle Rigging Blender Addon. 

We also need the design of the car and the wheels, you can downlad them from the following link (https://url.kr/gxv5yp) and remember where are they located. 

1. To install Blender, go to this website (https://www.blender.org/) and click on Download button.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/5fed6fd5-c1a0-4529-b6f1-2b8c060dd064)

2. Then click on Download Blender button. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/c8438115-773e-48d4-8cac-301dbde0976d)

3. Then open your Downloads folder, right click on the Blender file, and click on Extrat to. Then choose the location where you want that file to be extracted.

4. Go to the directory where the file was extracted and you will see a new folder. Double click on it, and then you can luanch blender by clicking the executable file. The image below shows which one should it be.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/da7f0058-188c-4d32-b042-5ab56310a1e8)

But if you want to be sure, you can right click on the item, then click on properties, and in the Type field, you will see that the file is executable if it looks like the image below. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/2ce81785-bd33-45a4-b008-992f88464172)

5. Once you open blender, it will ask you about the languaje, the theme of the app, please select them based on your preferences. And if there is a field you do not know what to fill it with, just leave the defualt configuration. Blender should look like this.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/52727a96-940a-4f0f-a300-6db89cd4b7ef)

6. To install the Add-on, first go to its website (https://continuebreak.com/creations/ue4-vehicle-rigging-addon-blender/). To download it, you just need to click on the the first link where says Download Here.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/9fed2d82-0678-4df3-8105-4e10777820e3)

7. To add that new addon to Blender, click on the Edit tab, and then, at the end of the drop-down menu, click on Preferences.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/5f8ca189-bd08-447e-aed4-fef8f41ed4c7)

8. Click on the Add-ons option in the sidebar, and then click on the Install button in the right top corner. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/a1f0973f-67ff-427d-916c-7daa4bd109d2)

9. Go to the directory where the Add-on was downloaded, and double click on it.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/9cc8e125-1313-4c2f-b3ae-0f3beb05ce2f)

10. In the search bar, type "Generic" and check the box of the "Generic: Unreal Engine 4 Vehicle Rigger" option.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/3be75834-f9e1-440f-8972-813bbc43504d)

11. Close the Blender Preferences window, and the press N. A small box will appear, you have to check that there is a tab called *UE4 Vehile*, that means that the Add-on has been applied successfully an it is enabled.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/f0aa2d00-58e2-4448-b88b-7e2daad44588)

12. Then restart Blender, and clik on the File tab, at the top menu. Then select New, and then General.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/95b2760e-653b-42a0-8e8e-31afe6415530)

13. Click on the Camera and press Delete to remove it, and do the same for the Cube and Light.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/56bc6338-1530-4b2a-a14e-6807b1442cfe)

14. Click on the File tab, then select Import, and click on *Collada(.dae)* option.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/f0d89fa0-26c5-40a6-8483-a285d18fd628)

15. Go to the location of the ``` .dae ``` files, and click the file of the body of the car. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/3e411112-1b5c-486e-b8a1-7f6b9a8c2c73)

16. Click on the Import COLLADA button.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/85e1e675-2192-42d1-8538-c9457a44aa30)

17. Then, following the table below, set the coordinates for the body of the vehicle. It is important that the car is facing the positive X axis, and you can locate and rotate the car in the Transform section, in the left sidebar.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/72dbaffd-b5d7-4e66-839a-c50760631d5a)

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/49aa11ba-af92-4ce2-9e9e-1b42972c36ec)

18. Repeat the same process with the wheels of the car, and locate them following the previous table, and rename them too by double clicking on the name of the file. It is possible that you may need to rotate the wheels, make sure that they are well-oriented. You should get something like this. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/9e070ed8-504a-4eda-a49a-5a1a87076393)

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/d0d80185-c0e3-4835-821d-0f1d6f69f24b)

19. Once the placement is complete, launch the Vehicle Rigging Blender Addon by pressing N on your keyboard and clicking on the 'UE4 Vehicle' tab. In the Vehicle rigging menu, match the Vehicle Base (Vehicle Body), Wheel FR (Front Right Wheel), Wheel RR (Rear Right Wheel), Wheel FL (Front Left Wheel) and Wheel RL (Rear Left Wheel) fileds with each part of the vehicle. To do that, click the blank space next to each field, and select the appropriate model. For our example, we matched them following this image. Make sure that every part is well-selected to avoid any future problem.
 
![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/3ff3c34c-3f2b-48ca-a6a1-8a034e581a8d)

20. Click the 'Upscale Objects' and 'Set Unit Scale' buttons to resize the objects, then click the 'Rig Vehicle' button to apply the armature to the vehicle. You will note that the vehicle gets bigger.

    You should get something like this.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/3fc1aa98-a80d-4996-8a22-d981c0cd5871)

21. In the Scene Collection on the right, select all the objects by clicking CTRL key, and clicking the following items.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/b95af6e9-eda3-443b-86d9-0e57bdc51d8d)

22. Click on File tab at the top of Blender, then select Export, and finally click on *FBX(.fbx)*

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/5f960f2b-5be1-4b8d-a46a-7fd5460879c5)

23. In the pop-up window, on the right side, please make sure that the following fields are filled out as follows:

    * In the Include menu, the *Limit to* field, check the box next to Selected Objects.
    * In the Object Types menu, select Armature and Mesh option. You can select both by keep pressing SHIFT key and clicking over those 2 options.
    * In the Geometry menu, set the Smoothing field with the Face option.
    * In Armature menu, uncheck the Add Leaf Bones checkbox.
   
Your setting should loook like this. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/0e80bda2-ab54-41aa-b0a9-bd017b7fd58a)

24. Name the file and click on Export FBX.
25. Select all the files again, like the image below.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/ec97404c-f87c-410b-a12c-84059ed4d147)

26. Under the File tab, there is another bar with around 4 or 5 options. There is also a drop-down menu, click on it and select Object Mode.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/b5413cfa-fb36-4751-a704-2df27a4fd8cc)

27. Click on the Object tab, and then on Join. You should not see any warning at the Blender's bottom.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/6da191af-bca9-41a8-9611-4dae555a9a1f)

You can also make this by using the shorcut CTRL+j

28. Create another ``` .fbx ``` file repeating from the step 22, but in the Object Types menu, select only mesh. The settings should be like the ones shown below. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/98e84a4d-63da-4640-baae-87192265af55)

You can also download the 2 resultant files from here:

https://o365skku-my.sharepoint.com/personal/jongsoo_o365_skku_edu/_layouts/15/onedrive.aspx?id=%2Fpersonal%2Fjongsoo%5Fo365%5Fskku%5Fedu%2FDocuments%2F%EC%97%B0%EA%B5%AC%EC%8B%A4%20%EC%9D%BC%2F%EA%B5%90%EC%9E%AC%EA%B0%9C%EB%B0%9C%28Carla%29%2FCARLA%20Resource%2F1%2ED%5F3%20ERP42%20model%28fbx%29&ga=1


## Applying a custom vehicle to the CARLA simulator

Adding a custom vehicle to the CARLA simulator is a complex process. The whole process takes place while CARLA simulator is running with make launch or make launch-only commands. If you make any mistakes, your car may not run, so follow the steps carefully. 

The sequence of steps is as follows:

1. Import 2 Vehicle Files Created in Blender
2. Setting up Physics
3. Animation Blueprint Settings
4. Setting Up the Wheel Blueprint
5. Setting Up a Vehicle Spawn Blueprint
6. Registering a custom vehicle in Vehicle Factory

Open carla simulator and follow the steps.

### 1. Import 2 Vehicle Files Created in Blender

1. Once CARLA is open, create a folder in the Content Browser to manage your customed vehicles, and double ckick on it.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/64875764-5140-434e-a9c7-0afdffc14155)

2. Click on Add/Import button, then on Import.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/22194261-7da3-4e2c-bf05-0ec3fcb1b57e)

3. Go to the path where the 2 previous files were exported.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/ca7bce9b-d662-4506-9884-dcf29226506a)

4. Click on Open, and then do not change anything and click on Import All.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/93920e0f-c419-4572-ac8a-e9a5001f88e2)

5. Repeat the process with the second ``` .fbx ``` file.
6. Once all the files are imported, the carpet that contains them should look like this.

Imagen

7. It is recommendable, based on Unreal Engine, to rename the files as the following table.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/b562ef99-40ab-49ea-9bf9-adc25955da58)

8. Once you have renamed all the files, you should have gotten something like this.

Imagen.

### Setting up Physics



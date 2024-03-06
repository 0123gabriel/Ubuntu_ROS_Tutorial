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
    * In the Tranform menu, in the "Forward" field select *X Forward", and in the "Up" field select "Z up".
    * In the Geometry menu, set the Smoothing field with the Face option.
    * In Armature menu, uncheck the Add Leaf Bones checkbox.
   
    Your setting should loook like this. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/a77e7e2d-39f1-4f60-a9ee-fd70a37c6be5)

24. Name the file and click on Export FBX.
25. Now, we need to export all the vehicle as one mesh, so you have to select the body of the vehicle, and the four wheels as follows. It is very important that you select first the 4 wheels and then the body of the vehicle, if you do not do that in that specific order, the parts will not join. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/62cdad55-c6b9-4066-ade1-eb890029367c)

26. Under the File tab, there is another bar with around 4 or 5 options. There is also a drop-down menu, click on it and select Object Mode.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/87efa62b-a95a-418f-b1c2-57edc139b192)

27. Click on the Object tab, and then on Join.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/bbac67b7-f6c4-4f62-a8e4-9f570d08d324)

You can also make this by using the shorcut CTRL+j.

Once they are joined as one part, you should see that if you click on any part the vehicle, the body and the wheels of it are going to be selected. Also take a look at the Scene collection, you won't have 5 parts anymore, you will have only 1. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/facbfaae-0528-4c7e-a02c-81f7c0cdb1ba)

28. Create another ``` .fbx ``` file repeating from the step 22, but in the Object Types menu, select only mesh. The settings should be like the ones shown below. Then name the file, and export it.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/92b429e1-a312-42e7-a360-20a93096d863)

You can also download the 2 resultant files from here:

(https://url.kr/gxv5yp)

## Applying a custom vehicle to the CARLA simulator

Adding a custom vehicle to the CARLA simulator is a complex process. The whole process takes place while CARLA simulator is running with make launch or make launch-only commands. If you make any mistakes, your car may not run, so follow the steps carefully. Also, this process might take a while.

The sequence of steps is as follows:

1. Import 2 Vehicle Files Created in Blender
2. Setting up Physics
3. Animation Blueprint Settings
4. Setting Up the Wheel Blueprint
5. Setting Up a Vehicle Spawn Blueprint
6. Registering a custom vehicle in Vehicle Factory

Open carla simulator and follow the steps.

### 1. Import 2 Vehicle Files Created in Blender

1. Once CARLA is open, create a folder in the Content Browser to manage your customed vehicles, and double ckick on it. I have created myVehicle folder.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/c55b2831-e9fe-4412-a2dc-7171d0a24259)

2. Right click and select Import to.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/130d367e-88bc-40e6-a8e4-e14eac8a2693)

3. Go to the path where the 2 previous files were exported.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/3936187a-e70b-4d7f-a89b-68e47734f460)

4. Click over the first exported file from Blender, and then hit Open. In the window that pops up, make sure that the following options are selected, and then click on Import All. This could take around 2 hours, and I also recommend that you should not use your computer until this process finishes, because using it might lead to a crash of Unreal Editor. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/14791107-45f8-4ce8-87f2-49661c2b0f04)

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/80265ee9-f2ea-4bbb-a1ed-4dc7754ec586)

Once the process has finished, you might get some errors, just ignore them and close the window. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/63f2afb1-5454-4210-bebf-3a4aa70084ee)

You will get 3 files. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/4416024d-b0b0-47c0-b4a6-fab0189ca359)

5. Repeat the process with the second ``` .fbx ``` file. Right click, then select Import to, hit the second file, and click on Open.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/3e14de37-47fa-4255-a1a5-6314e211e28e)

6. Make sure that the following options are checked.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/0c7c4807-ac26-4f2b-993b-9afdb5cfea94)

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/d92c0fcf-edf6-43f8-82f1-95d844c87924)

7. Then click on Import All. This will take around 30 minutes. And you might also get some errors, ignore them again and close the window. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/9da805e6-177b-481e-8cb7-bb068ebe056b)

Once all the files are imported, the folder that contains them should look like this.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/0eb73404-f1a2-4198-926a-b9e9b891b5d1)

8. It is recommendable, based on Unreal Engine advices, to rename the files as the following table.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/b562ef99-40ab-49ea-9bf9-adc25955da58)

8. Once you have renamed all the files, you should have gotten something like this.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/30fa8265-8474-4c12-b5e5-e47609f5b6e6)

### 2. Setting up Physics

1. Double click on the Physics Assets file. To know which one it is, you can move the mouse over every item, and a window with more information about the file will appear. In the information window, next to the name of the file you can check what type of file is that one. Another way to know that is the name we have setted, it should be PHYS_ERP42.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/7e8bfa22-ef9b-4b55-9e4a-dcaaec44a7fe)

After double clicking it, you should get this window. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/15c18b05-0017-476f-8131-3555cc386024)

2. In the Skeleton Tree on the left, click on Root.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/5ed43dd5-c2bc-44aa-a77a-23d328d77466)

3. In the Details section on the left, change the following 3 settings from the default settings.

   * In the Physics section change the Linear Damping field to zero (0).
   * In the Collision section, check the box next to Simulation Generates Hit Events.
   * In the Body Creation section, in the Primitive Type field, change it to Box option.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/fbe796e7-a54f-4318-8290-449c32b012a5)

4. Click on Re-generate Bodies.
5. Now select all the wheels in the Skeleton Tree section on the left by keep pressing CTRL key and clicking every wheel.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/9736037f-2c27-4b1c-9cde-88a7c452cb6e)
 
6. Change the following settings in the Details section on the left side.

   * In the Physics section change the Linear Damping field to zero (0).
   * In the Physics section change the Physics Type field to Kinematics.
   * In the Collision sectio, change the Collision Response to Disabled.
   * In the Body Creation section, in the Primitive Type field, change it to Sphere option.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/afe0c0ba-4034-4d8b-a4f3-d3e54a2b0e88)

7. Press the Re-generate Bodies button once again, and click anywhere. You should get something like this.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/cf261030-4bab-4f39-a30e-7ed8375080a3)

8. Close that window.

### 3. Animation Blueprint Settings

1. In the content browser directory where you have your new vehicle asset, right click and choose Animation and Animation Blueprint. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/5d17b2b6-3cf5-434c-b478-288192808e58)

2. In the popup that opens, search for VehicleAnimInstance in the Parent Class section and for the Target Skeleton search for the skeleton corresponding to your new vehicle, you should be able to see the name in your content browser. After selecting these two things press OK. This will create a new animation blueprint for your vehicle.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/651a8324-f860-4408-94b8-5fb0b176d7f8)

3. Rename the generated file to 'ABP_ModelName' (in this case ABP_ERP42), following Unreal Engine's recommended asset naming conventions.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/00a1decb-6c78-420f-80af-7be8d5c8f052)

4. Double-click on the generated file to run it.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/58a814bc-0976-4029-894c-986957f60d16)

5. Right click in the center of the window to add an action.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/166f6d17-2164-4786-bbfb-4bf4da907c8a)

6. Add the following blocks by clicking on them:

   * Wheel Handler for WheeledVehicle
     
     ![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/41dc9127-e19d-4d7b-b5e9-c0c9255f9e01)

   * Mesh Space Ref Pose
  
     ![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/006f85a8-e835-4bc1-8926-3119b0ba517f)

The AnimGraph should look like this. 
  
![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/987d8628-f36a-4f84-8359-306407b9cb9e)

7. Connect the Component Pose of the Mesh Space Ref Pose with the Component Pose of the Wheel Handler

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/c78c968d-543c-4f2d-bc79-1569de65d4b7)

8. Click on the small item of a person that is in the Wheel Handler and drag the mouse to connect it with the Output Pose. A block called "Component to Local" should appear in the middle of those 2 blocks.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/032c8ac1-4415-46f2-ae02-209d8518e10b)

9. Click on the Compile button which in the left top corner and then a flowing effect is added to the lines connecting the actions. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/5d6116d6-f6bf-4aa0-b377-4d20f15e872a)

10. Click on Save, and close the window. 

### 4. Setting Up the Wheel Blueprint

1. In the content browser directory where you have your new vehicle asset, right click and choose Blueprints and Blueprint Class. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/63a5f739-8e5c-401b-9e56-d8db3ad0c9df)

2. Select the wheel from a car (that appears in the search results) that you would like to reference. In our example, we have selected 'BP_AudiTT_FRW' and created a Wheel Blueprint file. Rename the file to 'BP_ModelName_Wheel' (in our case, the name should be BP_ERP42_Wheel) as any other file. That name follows the Unreal Engine's recommended asset naming conventions.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/77d4eb4c-16c8-4b98-af5e-ee50071b8835)

3. Double-click the generated file and enter the required values for your custom vehicle. This values are located in the right side. In our example, we used the following specifications.

   * The Shape Radious, Shape Width and Damping Rate fields are in the Wheel section.
   * The Steer Angle field is in the Wheels Setup section.
   * The Lat Stiff Max Load, Lat Stiff Value and Long Stiff Value fields are in the Tire section. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/23b1374d-a445-4fba-a8f4-a0ad8277d8e6)

4. Click on the Compile button in the right top corner, then on Save and close that window.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/8f293e14-1bee-484b-b865-1bf9676a893b)

### 5. Setting Up a Vehicle Spawn Blueprint

1. In the content browser directory where you have your new vehicle asset, right click and choose Blueprints and Blueprint Class. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/d02af31b-cd11-411b-8474-20abfb5f96ab)

2. In the All Classes menu, select BaseVehiclePawn and create a file named 'BP_ModelName_Pawn', in this case it should be BP_ERP42_Pawn. Then click on select.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/cefa8323-3b8a-4b8f-b3da-6045eeefced1)

3. Double click on the new file, and you will see the following window.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/a7848e68-075d-409f-a6f8-e5981d68ef75)

4. In the Components section in the left side, click on Mesh (VehicleMesh) (Inherited)

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/1113a7a5-444e-44c4-8868-5fcabd0c385f)

5. The details section on the right side needs to be modified as follows.

   * In the Mesh menu, change Skeletal Mesh from None to 'SM_ModelName', in this case SM_ERP42. Once you select it, you will see that the car appears in the center of the window. 
     
     ![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/faf78ba2-504d-4a8e-aac5-f9d53b5f3d69)

   * In the Animation menu, change Anim Class from None to 'ABP_ModelName', in this case ABP_ERP42.
     
     ![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/a97e3b5b-7e95-43a5-831c-3223f463dde5)

   * In the Physics menu, change the "x" and "y" components of the Center Of Mass Offsetx field to 0. It is possible that you might click on a downwards triangle with a straight line over it to open more options and find this field. 
  
     ![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/edf9b720-4910-4c19-ae2d-ca2f5b2b8d47)

6. In the Components section in the left side, click on "Vehicle Movement (MovementComp) (Inherited)"

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/adc89659-34f3-4245-b004-14c325900869)

7. The details of 'Vehicle Movement (MovementComp) (inherited)' need to be modified as follows.

   * In the Vehicle Setup menu, open the drop-down menu by clicking over Wheel Setups, and then repeat by clicking in every wheel. Then, for the 4 wheels set the Wheel Class to 'BP_ModelName_Wheel', in this case is 'BP_ERP42_Wheel'.

     ![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/9d1202ce-d292-47a5-a75b-0d776898461f)

   * Then, in the Bone Name field set a name for every wheel. Every wheel should already have a name, try to put a similar one. In my case I just delete the 'Wheel' part of the name by default. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/a29f809a-d2ca-4a19-9867-9f1bec7b04dd)

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/e52e1aef-8f10-4b50-9e7c-538415dd0f64)

   * In the Disable Steering field, check the box for the wheels that will not steer. They probably are the rear wheels. In my case, I check the boxes of the rear wheels.
  
![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/2531d616-93d9-4fd3-9461-259578ef25d3)
  
   * In the Mechanical Setup section set the Torque Curve, Engine Setup, Differential Setup and Transmission Setup according to the vehicle's specifications such as engine, transmission, etc. For this tutorial, the configuration is as follows.
  
     - **Torque Curve:** You have to have 7 points in total, to create them move the mouse where you want to create one, then right click  and select "Add Key to None". To set the coordinates of every point, click on the point and then click over the value next to Time and type the desired number, and make the same for the Value. 
    
       ![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/49ffa0e8-c5b2-4e4b-a843-e57db6bfaf09)
  
       ![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/a21faedb-c116-4c68-b14d-e370ef56dcc3)

     - **Engine Setup, Differential Setup, Transmission Setup, etc.**

       ![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/9e8fdd32-caf5-4604-8c94-81369704539b)

       You should get something like this for the **Mechanical Setup.** It is possible that in this section you will hace to delete some gears, you can do that by click the X at the end of the values of every  gear.  

       ![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/2f9069f8-7ee1-4d4b-a6e3-ce42b4c0e6cd)

       And with something like this for the **Vehicle Input**

       ![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/b5f84e32-ac41-4e50-a1fb-b028f015cfac)

       
8. In the Components section in the left side, click on "CustomCollision (Inherited)".

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/0c91eab2-c0c6-4281-bd95-d4398d22dddf)

9. In the Details panel on the right side, search the Static Mesh menu, and in the Static Mesh field select the 'SM_sc_ModelName', in this tutorial it should be 'SM_sc_ERP42'.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/aace1c54-09b6-4de8-8f2f-457581fb520f)

After clicking that, you should get something like this. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/93001eb1-64cf-47da-a6b8-dc99154eb772)

10. Click on Compile button and then on Save. Finally, close the window. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/a5418da6-1fa9-4e28-b17d-bbd52370e26d)

### 6. Registering a custom vehicle in Vehicle Factory

1. In the Content Browser go to the this directory: Content/Carla/Blueprints/Vehicles.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/33752080-d5e5-41c5-b5ad-cb665bd23be1)

2. Open the 'VehicleFactory' file, and in the centered window (the window with the grid) click on the 'Generate Definition' tab.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/03999b42-777b-4847-9d87-b0bbcecbd6d2)

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/85c8562e-6795-4e56-9ed0-b265c9265fd6)

3. Click the Vehicle node.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/e616ffb5-8307-4a9d-a79e-5755e5607bb2)

4. In the Details menu on the right, click on Default Value. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/30387e1e-f078-4593-8374-ac0f773d8e37)

5. Click the + icon for Vehicles and edit the newly created empty entry at the bottom.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/ffb46a2a-4783-46cc-9729-ab1603b0dec2)

6. Fill in the Make (this field is up to you, I typed UnmannedSolution) and Model (this field is up to you, but I typed ERP42) and select 'BP_ModelName_Pawn' (in this case is BP_ERP42_Pawn) for Class. Finally, set the Number Of Wheels to 4, Generation to 2, and Base Type to 'car'.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/532d1c2b-8876-4002-86b1-45854dfb0169)

7. Click on compile in the top right corner, and then on Save.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/a380a6dd-ed4c-49da-b74f-af3b0703e935)

8. Close the window, and you are done by adding a new vehicle!!! Congrats!!

To save everything, click in the File tab at the top, and select Save Current, and that's all!!

If you want to see how your vehicle is seen in your map, you can go to the directory where you save your map and doble click on the level file (the orange one). You can skip this step if you set that map as default. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/f6e787c0-1e81-4203-8fa9-88bda2bd9389)

Then go to the directory where you save your vehicle's files and drag the Skeletal Mesh file (or the one called SM_ERP42 or the pink one) to the window that is in the center. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/57fd2c3d-3c3e-4cf6-8360-3ea60778b96e)

You will see your vehicle in your map. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/f251bacd-c9c3-4680-ad6e-24f79d93baa0)


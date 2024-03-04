# Using a customed vehicle with CARLA

This task will need 2 apps: the first one is Blender and the other one is an Add-on for Blender which let us use the customed vehicle. This Add-on is called: Vehicle Rigging Blender Addon. 

We also need the design of the car and the wheels, you can downlad them from the following link (https://url.kr/gxv5yp) and remember where are they located. 

1. To install Blender, go to this website (https://www.blender.org/) and click on Download button.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/5fed6fd5-c1a0-4529-b6f1-2b8c060dd064)

2. Then click on Download Blender button. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/c8438115-773e-48d4-8cac-301dbde0976d)

3. Then open your Downloads folder, right click on the Blender file, and click on Extrat to. Then choose the location where you want that file to be extracted.

4. Go to the directory where the file was extracted and oyou will see a new folder. Double click on it, and then you can luanch blender by clicking the executable file. The image below shows which one should it be.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/da7f0058-188c-4d32-b042-5ab56310a1e8)

But if you want to be sure, you can right click on the item, then click on properties, and in the Type field, you will see that the file is executable if it looks like the image below. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/2ce81785-bd33-45a4-b008-992f88464172)

5. Once you open blender, it will ask you about the languaje, the theme of the app, please select them about your preferences. And if there is a field you do not know what to fill it with, just leave the defualt configuration. Blender should look like this.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/52727a96-940a-4f0f-a300-6db89cd4b7ef)

6. To install the Add-on, first go to its website (https://continuebreak.com/creations/ue4-vehicle-rigging-addon-blender/). To download it, you just need to click on the the first link where says Download Here.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/9fed2d82-0678-4df3-8105-4e10777820e3)

7. To add that new addon to Blender, click on the Edit tab, and then, at the end of the desplegable, click on Preferences.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/5f8ca189-bd08-447e-aed4-fef8f41ed4c7)

8. Click on the Add-ons option in the sidebar, and the click on the Install button in the right top corner. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/a1f0973f-67ff-427d-916c-7daa4bd109d2)

9. Go to the directory where the Add-on was downloaded, and double click on it.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/9cc8e125-1313-4c2f-b3ae-0f3beb05ce2f)

10. In the search bar, type "Generic" and check the box of the "Generic: Unreal Engine 4 Vehicle Rigger" option.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/3be75834-f9e1-440f-8972-813bbc43504d)

11. Close the Blender Preferences window, and the press N. A small box will appear, you have to check that there is a tab called *UE4 Vehile*, that means that the Add-on has been applied ans it is enabled.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/f0aa2d00-58e2-4448-b88b-7e2daad44588)

12. Then restart Blender, and clik on the File tab, at the top menu. Thne select New, and then General.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/95b2760e-653b-42a0-8e8e-31afe6415530)

13. Click on the Camera, Cube, and Light that are provided by default, press the delete key to remove them all.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/56bc6338-1530-4b2a-a14e-6807b1442cfe)

14. Click on the File tab, then select Import, and click on *Collada(.dae)* option.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/f0d89fa0-26c5-40a6-8483-a285d18fd628)

15. Go to the location of the ``` .dae ``` files, and open the body of the car. 

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/3e411112-1b5c-486e-b8a1-7f6b9a8c2c73)

16. Click on the Import COLLADA button.

![image](https://github.com/0123gabriel/Ubuntu_ROS_Tutorial/assets/108648272/4cc5679a-73d9-44fc-8824-408289229e22)

17. Then, following the table below, set the coordinates for the body of the vehicle. It is important that the car is facing the positive X axes.

 

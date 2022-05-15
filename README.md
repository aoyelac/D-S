# D-S
Comparative experiment of speed coordinated control methods based on D-S evidence synthesis theory

Experimental steps and precautions

Hardware:

1)	Computer: ASUS Desktop
2)	Operating system: Windows 10 Professional Edition 64 bit (Build 19041)
3)	Processor: 11th Gen Intel Core i7-11700K @ 3.60GHz 8 cores
4)	Memory: 16 GB (DDR4 2133 MHz)
5)	Disk: WDC WDS100T2B0C-00PXH0 
6)	Graphics card: Nvidia GeForce RTX 3060 (12 GB/ASUS )

Software:

1)	MATLAB: Version 9.6 (R2019a)
2)	Simulink: Version 9.3 (R2019a)
3)	Java: Java 1.8.0_181-b13 with Oracle Corporation Java Hot Spot (TM) 64-Bit Server VM mixed mode

Source file:

There are 28 files in the source code of this experiment, showing the model file\source code \experimental time verification and experimental results. The specific file name and purpose are shown in Fig. E1.

![image](https://user-images.githubusercontent.com/85392657/168475424-f949145d-fb53-4f69-bbea-eaf4a8bc86bb.png)

Fig. E1. The specific file name and purpose of the source file.

Experimental steps:

Step 1: Change the program running path to the source code file

1)	Open MATLAB R2019a.
2)	Click the button marked at 1 in red. 
3)	Find the source code file named “3-DOF experiment”. 
4)	Change the program running path to the source code, and execute step 1 in the current folder window, as shown in Fig. E2.

![image](https://user-images.githubusercontent.com/85392657/168475450-caf8a602-164c-4cf8-bf1b-c390d1ee1683.png)

Fig. E2. Execution process of step 1.

Step 2: Loading data required for the experiment

1)	After performing step 1, look for the file in Fig. E3 “Advance_Data_arm.mat” & “Advance_input_step.mat” marked at 2 in red. 
2)	Double click the above file or enter the command shown in box 3 in the command line window “load (’Advance_Data_arm.mat’)” & “load (’Advance_input_step.mat’)”, then load the database.
3)	After executing step 2, the workspace window is shown in Fig. E3. 

The loading data are described in detail below. The data required for the experiment are divided into two parts:

I.	“Advance_Data_arm.mat” records the parameters required by Simulink to build a three degree of freedom manipulator, including the centroid position of each component, moment of inertia, model color, position of each axis coordinate system and other information. After loading the database, the database information is stored in the simData for program operation. In addition, you can run “Advance_Data_arm.mat” to achieve the same result. 

II.	“Advance_input_step.mat” records the preset positions of the manipulator in the X, y and Z directions within 5 s during the continuous step task, and participates in the continuous step experiment as the path input.

![image](https://user-images.githubusercontent.com/85392657/168475509-b0027dac-d130-45e1-be00-96395908eb30.png)

Fig. E3. Execution process of step 2.

Step 3: Run Simulink to carry out the experiment of the ideal state space linear task.

1)	After executing step 2, click the Simulink button marked at 4 in Fig. E3 to prepare to run the Simulink program.
2)	Run Simulink, as shown in Fig. E4. Click the open button to open the simulation program, and find the source code folder in the list “3-DOF Experiment”.
3)	Click the code files marked at 3.1-3.4, which represent the space linear task simulation platform of the three degrees of freedom manipulator under cascade control, fuzzy control, adaptive fuzzy control and D-S evidence synthesis control. 

![image](https://user-images.githubusercontent.com/85392657/168475521-cae241d4-7bcd-4ca5-ae9b-c70d43cb5aef.png)

Fig. E4. Execution process of step 3.

Next, taking the D-S evidence synthesis controller ideal state space linear task simulation platform as an example, the simulation operation method of the simulation platform is introduced.

Step 4: Run the D-S evidence synthesis controller ideal state space linear task.

1)	Click to run the code file “DS_linear_1.slx” marked in box 3.4 in Fig. E4. The Simulink simulation control platform of the spatial linear motion of the 3-DOF manipulator based on the D-S evidence synthesis controller shown in Fig. E5 is obtained.
2)	Box 1 in Fig. E5 indicates the analytical formula of the spatial line. You can double-click the input box to change the analytical formula of the spatial line according to the task requirements.
3)	Click the start button marked in box 2 to start running the model.
4)	When the experiment is over, click the button marked in box 3 to check the track tracking error in the X, Y and Z axes.
5)	After the code file is run, a set of experimental output error arrays will be added to the workspace, shown as the box marked file in Fig. E6.
6)	After running all the code files indicated in boxes 3.1-3.4 in Fig. E4, the files added to the workspace are indicated in the box in Fig. E7.

![image](https://user-images.githubusercontent.com/85392657/168475541-eef2da27-aebd-453c-aa1d-d7480526544c.png)

Fig. E5. The Simulink simulation control platform of the D-S evidence synthesis controller.

![image](https://user-images.githubusercontent.com/85392657/168475558-97f9b13a-55c9-44d2-b1fa-dc0064f458a8.png)

Fig. E6. Experimental output error arrays. 

![image](https://user-images.githubusercontent.com/85392657/168475567-a209f1f8-bb79-4ba6-af6e-a02de1f47ced.png)

Fig. E7. Experimental output error arrays. 

Step 5: Carry out the continuous step task experiment under extremely bad conditions

The experiment simulates the extreme bad situation of serious failure and packet loss and disorder of sequence for a long time under the condition of large time delay of teleoperation. We preset that there is no protection mechanism of packet loss and disorder of sequence for the manipulator at this time. Under this input condition, the speed and acceleration of the ideal manipulator are infinite. By comparing the speed and acceleration under the control of different controllers, the adaptability of different controllers is obtained. The smaller the speed and acceleration are, the larger the adaptive range of the controller, that is, the better its adaptability. 

After executing step 2, click the Simulink button marked at 4 in Fig. E3 to prepare to run the Simulink program. Run Simulink, as shown in Fig. E8. Click the open button to open the simulation program, and find the source code folder in the list “3-DOF Experiment”. Click the code files marked at 3.1-3.4, which represent the space linear task simulation platform of the three degrees of freedom manipulator under cascade control, fuzzy control, adaptive fuzzy control and D-S evidence synthesis control. Next, taking the ideal state continuous step task simulation platform of the D-S evidence synthesis controller as an example, the simulation operation method is introduced.

1)	Click to run the code file “DS_step.slx” marked in box 3.4 in Fig. E8. The Simulink simulation control platform for the continuous step task of the 3-DOF manipulator based on the D-S evidence synthesis controller is obtained, as shown in Fig. E9.
2)	Box 1 in Fig. E9 indicates the step input, and then checks whether the workspace has preloaded the input information “input_x, input_y, input_z” and whether the program runs the ‘Advance_input_step.mat’ database. 
3)	Click the start button marked in box 2 in Fig. E9 to run the model.
4)	When the experiment is over, click the part marked in box 3 in Fig. E9 to check the speed and acceleration of each axis of the 3-DOF manipulator under the continuous step task.
5)	After the code file “DS_step.slx” is run, six groups of experimental output error arrays will be added to the workspace, as shown in the box marking part in Fig. E10. Where the tail is a, which represents the acceleration, and the number represents the axis.
6)	After running all the code files indicated in boxes 3.1-3.4 in Fig. E8, the files added to the workspace are indicated in the box in Fig. E11.
7)	Package and save the above running results to the result folder.

![image](https://user-images.githubusercontent.com/85392657/168475583-415ddf5d-852e-46de-823b-92524a26a53d.png)

Fig. E8. Run step 5.

![image](https://user-images.githubusercontent.com/85392657/168475869-1c92e767-b4d1-45be-b6b8-f03f5dd1fd67.png)

Fig. E9. The simulation platform for the continuous step task based on the D-S evidence synthesis controller.

![image](https://user-images.githubusercontent.com/85392657/168475880-17ea18e9-258a-4c7d-9c95-2a511475de14.png)

Fig. E10. Experimental output error arrays after running the code file “DS_step.slx”.

![image](https://user-images.githubusercontent.com/85392657/168475886-186ec168-3bc6-4e7d-bbde-f8947f812bd6.png)

Fig. E11. Experimental output error arrays after running Step 5.

Step 6: Record program running time

The running time here is the time required to complete the space linear task simulation task on the Simulink simulation platform and does not represent the real control running time. However, because all files have the same architecture except for different controllers, they can represent the computational complexity between different controller algorithms to a certain extent.

1)	As shown in Fig. E4, find all code files marked in boxes 3.1-3.4 and open them.
2)	Find “time_calculation.m” in the source folder, as indicated in box 1 of Fig. E12.
3)	Click the start button marked in box 2 in Fig. E 12 to start running the code.
4)	Check the time required for the operation of each model in command windows, as shown in box 3 in Fig. E12. The top-down methods of window display time are cascade controller, fuzzy control, adaptive fuzzy control and D-S evidence synthesis control. 

Note: Affected by the hardware performance, the running time of each model will be slightly different each time. The current running time is shown in Table 1.

![image](https://user-images.githubusercontent.com/85392657/168475908-f556b92f-7ace-4b87-9ba9-0d6250596f81.png)

Fig. E12. Execution process of step 3.

Table 1
Record program running time
![image](https://user-images.githubusercontent.com/85392657/168475952-e6996d42-f89b-46c9-9556-08835a827f60.png)

Through comparison, it is found that the algorithm complexity of cascade control is the lowest, and the algorithm complexity of D-S evidence synthesis theory control is much lower than that of fuzzy control and adaptive fuzzy control.

#Possible errors and solutions：

Error 1: Error evaluating parameter ’Mass’ in ’XXX’ Undefined variable ”smiData” or class ”smiData.Solid”.

Solution: Please re execute Step 1 and Step 2. Double click to load the file ’Advance_Data_arm.mat’, or enter the command ”load(’Advance_Data_arm.mat’)” at the command line window.

Error 2: Invalid setting in ’XXX’ for parameter ’VariableName’.

Solution: Please re execute Step 1 and Step 2. Double click to load the file ’Advance_Data_arm.mat’, or enter the command “load(’Advance_Data_arm.mat’)” at the command line window.

Error 3: The program can run smoothly, but the manipulator cannot be observed in the simulation interface (Fig. E13).

![image](https://user-images.githubusercontent.com/85392657/168476006-c8a90c77-ca61-44fc-940c-5dc53f23ab74.png)

Fig. E13. Execution process of step 3.

Solution: Model addressing error due to file movement. The solution is as follows:

1)	Click the stop button marked in box 1 in Fig. E14 to end the program. 
2)	Check whether the source code model file is missing. The model code file is shown in Fig. E15. 
3)	Click the part marked in box 2.1 of Fig. E14 to enter the interface shown in Fig. E16. Click the part marked in box 1 of Fig. E16 to obtain the interface marked in box 2 of Fig. E16. 
4)	Click Fig. E16 For the part marked in box 3, click the "model" marked in box 4 in the pop-up file list_ 0_ base. STEP”. 
5)	According to the above methods, the marked parts of boxes 2.2-2.5 in Fig. E16 are modified successively, and the selected contents are as follows: 
2.2: ”Model_1_Joint0.STEP”
2.3: ”Model_2_Leg1.STEP”
2.4: ”Model_3_Leg1.STEP”
2.5: ”Model_5_Prob.STEP”
6)	Click Fig. E14 Click the run button marked in box 3 to run again. 

![image](https://user-images.githubusercontent.com/85392657/168476042-04de347a-df26-4a81-bd2c-b3109e79af6a.png)

Fig. E14. The simulation platform for the continuous step task based on the adaptive fuzzy controller.

![image](https://user-images.githubusercontent.com/85392657/168476052-5f3e6d89-a23a-4647-b2fd-07996244ab90.png)

Fig. E15. Files of the manipulator model.

![image](https://user-images.githubusercontent.com/85392657/168476056-763d26b8-06e9-4bd9-9c7e-fd5381ae76b7.png)

Fig. E16. Solution of error 3.

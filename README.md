# WRO_SCiUS_MSU

Introduction 

 

The car which is used in the competition has 2 motors (Large motor and medium motor) and 3 sensors (Color sensor, Gyro sensor, Husky Lens sensor). The car uses a Parallel Steering System to move forward, using large motor and medium motor.  

‘ 

 

Large motor 

The motor is placed on the back of the car vertically and has 2 gears to labor the force. 

 

Medium motor 

The motor is placed in the middle of the car controls the front wheels in Parallel steering system by rotating the gears to move gear rack which can switch the direction of the wheels  

 

Color sensor 

The sensor is placed in the front of the car, used for detecting lights and colors on the field. 

 

Gyro sensor 

The motor is placed near the medium motor, used for changing the degree of the car.  

 

Husky Lens sensor 

The sensor is placed at the top of the car, used for reading the traffic lights to decide the direction. 

 

 

Part one: No traffic lights 

In terms of algorithms, we will use the principle of turn back then run straight to prevent erroneous turns but will only reverse and turn when it sees orange color on the ground. We have the function main file GOGOG.evp3 and all 7 sub-functions which will explain later.  

 

Variable 

There are 6 variables in our code: 
1. Speed ​​is used to determine the speed of the car. Here we will use 40 units. 
2. Turn determines the angle of the wheels to move. Here we will use 60 degrees. 
3. count is the number of laps that the wheel has been broken. Here we start at 0. 

4. CWorCWW (Clockwise or Counter Clockwise) determines whether In this game, we will have to walk clockwise or counterclockwise. Default = 0, clockwise = 1 and counterclockwise = 2. 

5. FTurn is a Treshol level that will determine the direction of the car when passing the orange line. Here we will use 26 degrees. 
6. STurn is a Treshol level that will determine the direction of the car when passing the blue line. Here we will use 90 degrees. 

Community Verified icon 

 

Main Function (GOGOGO.ev) 

The first part is to define the variables as shown in the picture. After that, it will loop infinity by checking 3 things: 

 
1. To check the count, we have to make a total of 3 laps around the field or make a total of 12 turns. After the turn is complete, run a little more and then stop. 

 
 

After checking that it is not complete, there will be a sub loop to wait for the color that the color sensor detects. 
 
2. Orange check, if you find color number 4 or 5 (yellow or red), you will check first if it's a clockwise or counter-clockwise walk. If it is a walk in a needle It will call the YellowFirst function. 
 When done, it will set the variable to be clockwise again. (It will be useful when the first time you see orange. so you don't have to think about working when you see blue) and then exit this loop. 

 

3. Blue check If the color number 1 or 2 (black or blue) is found, it will check first if it is a clockwise or anti-clockwise walk. If it's a reverse walk, it will call the BlueFirst function. 
 When done, it will set the variable to turn counterclockwise again. (It will be useful when the first time you see the blue so you don't have to think about working when you see orange) and then exit this loop. 

 

 
After exiting the sub-loop, it will reset the gyro and perform the CountUp function. 

 

The YellowFIrst function in the Main Function is a function that retrieves the Turn and Speed ​​values ​​for the Action1O and Action2O functions. 

 

The Acton1O function in the YellowFirst function stops the Large Motor and turns the Medium Motor to adjust the direction of the front wheels. Then it will rotate the Large Motor to make the car go backwards until the Gyro Sensor has reached the FTurn value and will stop the car and return the wheels to keep the car straight. 

 

The Action2O function follows the Acton1O function. It starts by rotating the Large Motor until the Color Sensor reaches a value of 1 or 2 (black or blue detected), then stops the Large Motor and rotates the Medium Motor according to the value. Turn to adjust the front wheel direction and turn the Large Motor to move the car to the side until the Gyro Sensor has reached the STurn value, then stop the car and return the wheel and continue running. 

 

The BlueFIrst function in the Main Function is a function that retrieves the Turn and Speed ​​values ​​for the Action1B and Action2B functions. 

 

The Acton1B function in the BlueFIrst function stops the Large Motor and turns the Medium Motor to adjust the direction of the front wheels. Then it will rotate the Large Motor to make the car backwards until the Gyro Sensor reaches -FTurn value and will stop the car and return the wheels to keep the car straight. 

The Action2B function follows the Acton1B function. It starts by rotating the Large Motor until the Color Sensor reaches a value of 4, 5 or 7 (yellow, red or brown detected), then stops the Large Motor and Turn the Medium Motor according to the Turn value, adjust the front wheel direction and turn the Large Motor to the side until the Gyro Sensor reaches -STurn value, then stop the car and return the wheel and continue running. 

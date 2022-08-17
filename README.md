# WRO_SCiUS_MSU

## TEAM DETAILS: 

**Team name:** SCiUS MSU 

**Country:** Thailand 

**Team members:** 

- Pasit Khumsena 

- Pattarathida Khunthula 

- Suphapit Udom 

**Coach:** 

- Suchart Osaklang 

- Wutthisat Chokkuea

## Team photos: 

Official photo 

![This is an image](https://i.imgur.com/VdVHBgR.jpeg)

Funny photo 

![This is an image](https://i.imgur.com/Jig8csK.jpeg)

## Vehicle photos: 

FRONT VIEW 

![This is an image](https://i.imgur.com/adjppHZ.jpg)

BACK VIEW 

![This is an image](https://i.imgur.com/5sDMh65.jpg) 

LEFT VIEW 

![This is an image](https://i.imgur.com/VyIrx52.jpg)

RIGHT VIEW 

![This is an image](https://i.imgur.com/DfpC5OJ.jpg)

TOP VIEW 

![This is an image](https://i.imgur.com/zWMznZU.jpg)  

BOTTOM VIEW

![This is an image](https://i.imgur.com/H5MlbpJ.jpg)

## Video

https://www.youtube.com/watch?v=1VzLGnLJ_HQ&t=3s

## Introduction 

 

The car which is used in the competition has 2 motors (Large motor and Medium motor) and 3 sensors (Color sensor, Gyro sensor, Husky Lens sensor). The car uses a Parallel Steering System to move forward, using large motor and medium motor.  

![This is an image](https://i.imgur.com/XYla45S.jpg)

 

### Large motor 

The motor is placed on the back of the car vertically and has 2 gears to labor the force. 

 

### Medium motor 

The motor is placed in the middle of the car controls the front wheels in Parallel steering system by rotating the gears to move gear rack which can switch the direction of the wheels  

 

### Color sensor 

The sensor is placed in the front of the car, used for detecting lights and colors on the field. 

 

### Gyro sensor 

The motor is placed near the medium motor, used for changing the degree of the car.  

 

### Husky Lens sensor 

The sensor is placed at the top of the car, used for reading the traffic lights to decide the direction. 

 

 

## Part one: No traffic lights 

In terms of algorithms, we will use the principle of turn back then run straight to prevent erroneous turns but will only reverse and turn when it sees orange color on the ground. We have the function main file *GOGOG.evp3* and all 7 sub-functions which will explain later.  

 

### Variable
![This is an image](https://i.imgur.com/nlOreTW.png)

There are 6 variables in our code: 
1. **Speed** ​​is used to determine the speed of the car. Here we will use 40 units. 
2. **Turn** determines the angle of the wheels to move. Here we will use 60 degrees. 
3. **count** is the number of laps that the wheel has been broken. Here we start at 0. 
4. **CWorCWW** (Clockwise or Counter Clockwise) determines whether In this game, we will have to walk clockwise or counterclockwise. Default = 0, clockwise = 1 and counterclockwise = 2. 
5. **FTurn** is a Treshol level that will determine the direction of the car when passing the orange line. Here we will use 26 degrees. 
6. **STurn** is a Treshol level that will determine the direction of the car when passing the blue line. Here we will use 90 degrees. 

Community Verified icon 

 

###  Function (GOGOGO.ev) 

The first part is to define the variables as shown in the picture. After that, it will loop infinity by checking 3 things: 

1. To check the count, we have to make a total of 3 laps around the field or make a total of 12 turns. After the turn is complete, run a little more and then stop. 

![This is an image](https://i.imgur.com/b1PUjSW.png)

After checking that it is not complete, there will be a sub loop to wait for the color that the color sensor detects. 

2. Orange check, if you find color number 4 or 5 (yellow or red), you will check first if it's a clockwise or counter-clockwise walk. If it is a walk in a needle It will call the YellowFirst function. 
 When done, it will set the variable to be clockwise again. (It will be useful when the first time you see orange. so you don't have to think about working when you see blue) and then exit this loop. 

![This is an image](https://i.imgur.com/O7zV4G1.png)

3. Blue check If the color number 1 or 2 (black or blue) is found, it will check first if it is a clockwise or anti-clockwise walk. If it's a reverse walk, it will call the BlueFirst function. 
 When done, it will set the variable to turn counterclockwise again. (It will be useful when the first time you see the blue so you don't have to think about working when you see orange) and then exit this loop. 

![This is an image](https://i.imgur.com/s6O6cxy.png) 
 
After exiting the sub-loop, it will reset the gyro and perform the CountUp function. 

![This is an image](https://i.imgur.com/WewveEm.png)

The YellowFIrst function in the Main Function is a function that retrieves the Turn and Speed ​​values ​​for the Action1O and Action2O functions. 

![This is an image](https://i.imgur.com/YoHKCD8.png)

The Acton1O function in the YellowFirst function stops the Large Motor and turns the Medium Motor to adjust the direction of the front wheels. Then it will rotate the Large Motor to make the car go backwards until the Gyro Sensor has reached the FTurn value and will stop the car and return the wheels to keep the car straight. 

![This is an image](https://i.imgur.com/5brq7T3.png)

The Action2O function follows the Acton1O function. It starts by rotating the Large Motor until the Color Sensor reaches a value of 1 or 2 (black or blue detected), then stops the Large Motor and rotates the Medium Motor according to the value. Turn to adjust the front wheel direction and turn the Large Motor to move the car to the side until the Gyro Sensor has reached the STurn value, then stop the car and return the wheel and continue running. 

![This is an image](https://i.imgur.com/2G92ofW.png)

The BlueFIrst function in the Main Function is a function that retrieves the Turn and Speed ​​values ​​for the Action1B and Action2B functions. 

![This is an image](https://i.imgur.com/DrnOGHk.png)

The Acton1B function in the BlueFIrst function stops the Large Motor and turns the Medium Motor to adjust the direction of the front wheels. Then it will rotate the Large Motor to make the car backwards until the Gyro Sensor reaches -FTurn value and will stop the car and return the wheels to keep the car straight. 

The Action2B function follows the Acton1B function. It starts by rotating the Large Motor until the Color Sensor reaches a value of 4, 5 or 7 (yellow, red or brown detected), then stops the Large Motor and Turn the Medium Motor according to the Turn value, adjust the front wheel direction and turn the Large Motor to the side until the Gyro Sensor reaches -STurn value, then stop the car and return the wheel and continue running. 

## Part two: Traffic lights

The overall composition is the same as the first part, but with the addition of a condition: traffic light check using the function name HuskyCheck 
 
HuskyCheck detects objects in a specified distance. Here it is set at 60 units. You need to know the color of the traffic light for decision making. The green traffic light ID is 1 and the red traffic light ID is 2. It will be considered separately by the GreenFound and RedFound functions. 

![This is an image](https://i.imgur.com/FFmrba0.png)

### GreenFound
 
Once we have found green in our realm We will consider the location of the traffic lights first. By using the LeftOrRight function, if the traffic light is on the right or left hand side of the car while the car runs according to traffic rules. 

![This is an image](https://i.imgur.com/hF5fYH3.png)

But if the traffic lights Not in the condition of Function, our car will try to turn left for the correct Function LeftOrRight. If so then Slowly return the wheel and run straight. 

![This is an image](https://i.imgur.com/t3ttGMj.png) 

### RedFound
 
Similar to GreenFound, but if the Function LeftOrRight condition is not met, it will try to turn right instead. 

![This is an image](https://i.imgur.com/btUB7IX.png)

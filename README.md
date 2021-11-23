# ARDUINO-BASED-WIRE-BENDING-MACHINE

![image](https://user-images.githubusercontent.com/19898602/143078943-2f38df45-34d4-4694-be19-fb0536a4b28e.png)


Fancy making yourself your very own Arduino-powered DIY wire bending machine? With a few extra parts, like stepper motors and some 3D printed parts, you can do just that with this great tutorial.

Before you start, you will need to get your hands on some basic components. We have included links to the products in case you need to buy them: 

> 1 no. Mini Nano V3.0

> 2 no. Aibecy Creality 3D Printer Stepper

> 2 no. BIQU A4988 Stepper Driver Module

> 1 no. WINSINN filament feeder

> Various 3D printed parts. 

> Spool of brass wire

> 5 no. 693ZZ Ball Bearing

> 1 no. 1K ohm resistor

> 1 no. 3D printer filament feeder

> PCB board or breadboard for creating the circuit

> 8mm MDF board or similar

> M4 nuts and bolts for mounting to MDF board

This great little wire bending machine can turn basic brass wire into some interesting; geometric shapes like a triangle, square, rectangle, hexagon, and even a spiral!

Of course, you can also experiment with the parameters to create any shape, within reason, you like from the serial monitor. The project is fun to build on your own, but will also go perfect as a classroom project too.

The first part is to wire everything up. Here is the circuit diagram: 


![image](https://user-images.githubusercontent.com/19898602/143079215-532e7946-5083-42e8-8c4e-ecd1b94d2ae6.png)


You can either solder the components to a PCB board or connect up using a breadboard. The choice is yours. 

Next, you will need to 3D print some additional parts. You can check out the 3D print files here. If you don't have access to a 3D printer yourself, why not ask a friend to help you out?

The parts will need to be printed in PLA at 0.15 layer height with 80% infill.

Once in hand, you will then need to begin assembling the parts. Use the bolts and nuts to affix the 3D parts to the MDF board, as well as, mounting bearings and stepper motors to their respective positions; as shown in the video.

You will also need to mount a 3D printer filament feeder to feed the brass wire into the machine from the ball bearing straightner assembly.

With all the parts assembled, it is time to sort out another critical component -- the actual code for the Arduino. We have included it in full below, but if you want an explanation of its various parts, see here. 



I have use arduino nano for this project, this machine can shape wire in some 2D geometrical figures.
I have write code for some 5 basic shapes like, Triangle, Square, Rectangle, Hexagon & spiral.
What shape and size you want to bend can be define from serial monitor.


In this way it became very flexible and user friendly, don’t need to upload new code for new shape.
More complex shape can also possible, for that we need to write code and upload to arduino.


This DIY Arduino based 2D wire bending machine is fun to build on your own, if you are students this will be good project for your academic project.

# VIDEO

Watch the video of DIY Arduino based 2D wire bending machine for complete information about how to build this machine or you can also continue to read the post.

https://youtu.be/HpuprEfqoEk

# COMPONENT REQUIRED

Followings are the major components require to build DIY Arduino based 2D wire bending machine


> Arduino nano — 1 no.

> Nema 17 stepper motor — 2 nos.

> A4988 stepper driver module — 2 nos.

> Filament feeder — 1 nos.

> 3D printed parts

> 1 Sqmm brass wire

> 3mm bearing 693ZZ — 5 nos.

> M4 nuts and bolts for mounting


# CIRCUIT DIAGRAM

![image](https://user-images.githubusercontent.com/19898602/123724744-7f7efa00-d8aa-11eb-91f7-e7e355882e07.png)


Refer the above circuit diagram to do wiring, I have use 12V 2A external power supply to power arduino and stepper motor.
A4988 driver module is use to operate Nema17 stepper motor, 

if your stepper motor get unstable or moving some random steps during start up so you can connect step pin and GND pin with 1K ohm resistor.

Bender motor direction pin is connected with - A0 pin of arduino

Bender motor step pin is connected with - A1 pin of arduino 

Feeder motor direction pin is connected with - A2 pin of arduino 

Feeder motor step pin is connected with - A3 pin of arduino

A4988 Stepper driver is set at 16 microstepping setting by giving 5V to MAS1 MS2 & MS3 pin of driver


# PCB

![FTQFHXZKLBNXU2X](https://user-images.githubusercontent.com/19898602/123725479-bd305280-d8ab-11eb-8709-c680e91e1300.jpg)
![MVI_0001_2 mp4 00_06_55_14 Still001](https://user-images.githubusercontent.com/19898602/123725534-d5a06d00-d8ab-11eb-9645-d2a05880e79a.jpg)
![MVI_0001_2 mp4 00_07_11_00 Still002](https://user-images.githubusercontent.com/19898602/123725542-d933f400-d8ab-11eb-9a7f-d88351d6a952.jpg)

I designe this multipurpose PCB Those who ever worked with arduino they know the pain of connecting multiple components to the arduino for there projects. so here is the answer for you all.

Not only 2 or 3 you can connect 11 components at same time & on board 5V & 9V regulator,

cross polarity protection, power indication LED,

motor power selection provision (5V or 9V or 12V) manual provision for stepper motor microstepping setting.

Wide range of input supply (9V to 24V). This is my multipurpose PCB works with Arduino Nano, I have designed it in a way that you can run 2 Stepper motors, 2 DC motors, 2 Servo motors at same time and this is not it you can even connect BT module, rotary encoder, I2C device, potentiometer at same time.

This PCB is very much helpful in building any project and no need to worry about messy wire connections.

![image](https://user-images.githubusercontent.com/19898602/123725769-50698800-d8ac-11eb-83b0-fbdab6a23ec1.png)
![image](https://user-images.githubusercontent.com/19898602/123725784-5a8b8680-d8ac-11eb-9a51-bb9042d974ec.png)


He we first see the overview of PCB means what is this PCB capable of and which components you can connect to the PCB.

# List of the Components you can connect to the PCB

> 2 DC motor ( 9V to 24V DC)

> 2 Potentiometer

> 2 Servo motors ( 5V to 9V DC)

> 1 Serial device (BT module, HMI, Communication module, RX, TX)

> 1 Encoder (2 interrupt pin & 1 PB pin)

> 1 I2C device (SCL/SDA Device, display, MPU6050 etc)

> 2 Stepper motors


# Special features of PCB

> Wide range of power input 9V to 24V DC

> Cross polarity protection

> DC motor voltage selection 9V or 12 V DC

> Servo motor voltage selection 5V or 9V DC

> Manual microstepping setting for stepper motor

> Power indication LED

> L298N IC for heavier DC motor

> ON board 5V and 9V regulator no need to arrange different power sources

> Header pins and screw terminals for easy connections




I have designe this PCB and order it from [JLCPCB.com](https://jlcpcb.com/IAT)

I always prefer [JLCPCB.com](https://jlcpcb.com/IAT) for my PCB needs, [JLCPCB.com](https://jlcpcb.com/IAT) have best deals for their customers
$2 for 1-4 Layer PCBs, free SMT assembly monthly.


If new user signup today from this link [JLCPCB](https://jlcpcb.com/IAT ) you will get 30$ coupon from [JLCPCB](https://jlcpcb.com/IAT ).


[Click here to visit JLCPCB.com](https://jlcpcb.com/IAT)



# 3D FILES

![image](https://user-images.githubusercontent.com/19898602/123726078-f0bfac80-d8ac-11eb-87d5-7dd0cbf31be8.png)


I have uploaded all the required [3D parts](https://www.thingiverse.com/thing:3789571) at thingiverse
you can download it and print it, I have printed all parts in PLA and 0.15 layer height and 80% infill on tevo [terantula 3d printer](https://amzn.to/2KhMkPb)

# WIRE BENDING MACHINE ASSEMBLY

![image](https://user-images.githubusercontent.com/19898602/123726153-177de300-d8ad-11eb-82e6-64e0b92af6e9.png)


First of all I printed all the required 3D parts in PLA material.

![image](https://user-images.githubusercontent.com/19898602/123726171-1fd61e00-d8ad-11eb-8962-965bc0da7665.png)


I mount the parts on 8MM mdf board using M4 bolts and nuts.

![image](https://user-images.githubusercontent.com/19898602/123726192-26fd2c00-d8ad-11eb-93d9-cb7b07a1833f.png)


After that I assemble the wire straightener system, I have used 3mm bore diameter bearing 693ZZ

![image](https://user-images.githubusercontent.com/19898602/123726203-2c5a7680-d8ad-11eb-9464-fd63bda3ef44.png)


Next I mount both stepper motor, I have used 3D printer filament feeder to feed brass wire in machine.

![image](https://user-images.githubusercontent.com/19898602/123726216-34b2b180-d8ad-11eb-8f54-45991ef7c068.png)  ![image](https://user-images.githubusercontent.com/19898602/123726225-3aa89280-d8ad-11eb-9080-175e3e4c391d.png)


Now I mount the bending arm on the shaft of stepper motor, and next I mount the wire guider on the feeder stepper motor mount.

![image](https://user-images.githubusercontent.com/19898602/123726248-45632780-d8ad-11eb-8d59-fe5148b92f71.png)  ![image](https://user-images.githubusercontent.com/19898602/123726256-48f6ae80-d8ad-11eb-90d7-ccef89903c41.png)  ![image](https://user-images.githubusercontent.com/19898602/123726260-4bf19f00-d8ad-11eb-937d-f74c4c2e64d1.png)


At last I mount a roller bearing to hold the roll of wire, then PCB is mounted on MDF Board and stepper motion is connected to there terminal.
Here machine assembly is almost done so now we can move towards arduino code.




 
# HOW TO OPERATE WIRE BENDING MACHINE

![image](https://user-images.githubusercontent.com/19898602/123726352-6fb4e500-d8ad-11eb-8553-a85f5e952be1.png)


Connect the power supply to the system, connect arduino and PC with USB cable.
Open the Arduino IDE software launch the serial monitor immediately you will receive a massage to input the data.
suppose you want to make a triangle of 20mm lenght so you need to enter
1,20
The first number before comma is for shape selection and the number after comma are side length.

That’s all for now friends.
If you like this project or have any question regarding, please ask it in the comment section below.







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


```


#include <Arduino.h>
#include "BasicStepperDriver.h"


#define Feed_step 200
#define Bend_step 200
#define Feed_RPM 80
#define Bend_RPM 30


#define MICROSTEPS 16
#define FEEDSTEPS 8
int Delay = 50;

#define Bend_DIR 14
#define Bend_STEP 15
#define Feed_DIR 16
#define Feed_STEP 17
int val = 0;
int data = 0;
int a = 0;
int b = 0;
int c = 0;

BasicStepperDriver Feed_stepper(Feed_step, Feed_DIR, Feed_STEP);

BasicStepperDriver Bend_stepper(Bend_step, Bend_DIR, Bend_STEP);



void setup() {
  Serial.begin(9600);
    Feed_stepper.begin(Feed_RPM, MICROSTEPS);
    Bend_stepper.begin(Bend_RPM, MICROSTEPS);
    Serial.println("For Triangle enter (1,Side Length) ");
    Serial.println("For Square enter (2,Side Length) ");
    Serial.println("For Rectangle enter (3,Height,Length) ");
    Serial.println( "For Hexagon enter (4,Side Length) ");
    Serial.println( "For Spring enter (5,Spring Length) ");
    Serial.println( "**Note Enter value without bracket ");
}

void loop() {
  if (Serial.available()>0){

a = Serial.parseInt();
b = Serial.parseInt();
c = Serial.parseInt();
  }


if (a == 1){
  Serial.println("  ");
  Serial.print("Making Triangle of side Length "); 
  Serial.print(b);
  Serial.println("mm");
for (int x=0; x<3; x++){
  Serial.println("..");
  Feed_stepper.move(FEEDSTEPS*b*MICROSTEPS);
  delay(Delay);
  Bend_stepper.rotate(95);  
  delay(Delay);
  Bend_stepper.rotate(-95);
  }
  Feed_stepper.move(FEEDSTEPS*15*MICROSTEPS);
  Serial.println("Finish ");
  a = 0;
  b = 0;
}


  
if (a == 2){
  Serial.println("  ");
  Serial.print("Making Square of side Length "); 
  Serial.print(b);
  Serial.println("mm");
for (int x=0; x<4; x++){
  Serial.println("..");
  Feed_stepper.move(FEEDSTEPS*b*MICROSTEPS);
  delay(Delay);
  Bend_stepper.rotate(75);  
  delay(Delay);
  Bend_stepper.rotate(-75);
  }
  Feed_stepper.move(FEEDSTEPS*15*MICROSTEPS);
  Serial.println("Finish ");
  a = 0;
  b = 0;
}


if (a == 3){
  Serial.println("  ");
  Serial.print("Making Rectangle of  Length & Height "); 
  Serial.print(b);
  Serial.print(" & ");
  Serial.print(c);
  Serial.println(" mm");
  Serial.println("..");
 for (int x=0; x<2; x++){ 
  Feed_stepper.move(FEEDSTEPS*b*MICROSTEPS);
  delay(Delay);
  Bend_stepper.rotate(75);  
  delay(Delay);
  Bend_stepper.rotate(-75);
  delay(Delay);
  Feed_stepper.move(FEEDSTEPS*c*MICROSTEPS);
  delay(Delay);
  Bend_stepper.rotate(75);  
  delay(Delay);
  Bend_stepper.rotate(-75);
 }
 Feed_stepper.move(FEEDSTEPS*15*MICROSTEPS);
  Serial.println("Finish ");
  a = 0;
  b = 0;
}


if (a == 4){
  Serial.println("  ");
  Serial.print("Making Hexagon of Side Length "); 
  Serial.print(b);
  Serial.println("mm");
for (int x=0; x<5; x++){
  Serial.println("..");
  Feed_stepper.move(FEEDSTEPS*b*MICROSTEPS);
  delay(Delay);
  Bend_stepper.rotate(70);  
  delay(Delay);
  Bend_stepper.rotate(-70);
  }
  Feed_stepper.move(FEEDSTEPS*15*MICROSTEPS);
  Serial.println("Finish ");

a = 0;
  b = 0;
}



if (a == 5){
  Serial.println("  ");
  Serial.print("Making Spring of Length "); 
  Serial.print(b);
  Serial.println("mm");
for (int x=0; x<b*5; x++){
  Serial.println("..");
  Feed_stepper.move(360);
  delay(Delay);
  Bend_stepper.rotate(60);  
  delay(Delay);
  Bend_stepper.rotate(-60);
  }
  Feed_stepper.move(FEEDSTEPS*15*MICROSTEPS);
  Serial.println("Finish ");
  a = 0;
  b = 0;
}

}
    

````

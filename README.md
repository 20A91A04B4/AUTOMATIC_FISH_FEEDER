# AUTOMATIC_FISH_FEEDER
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>TITLE OF PROJECT: AUTOMATIC FISH FEEDER USING SERVOMOTOR>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>

ABSTRACT:The idea is to design a system that dispenses fish food at specified intervals using a servo motor to control the feeding mechanism.
This code simulates the operation of an automatic fish feeder using a servo motor. It keeps the servo closed during the feeding interval, 
then gradually opens and closes it to dispense food. 

APPARATUS:
1.ARDUINO CABLE
2.ARDUINO UNO BOARD
3.SERVOMOTOR
4.MALE TO MALE WIRE
5.PLASTIC BOTTLE
6.SMALL STAND
7.FISH FOOD

TOOLS:
1.Drill
2.Glue 
3.Computer (to code)

PROCEDURE:
1.Take apparatus requried to PROJECT.
2.Using a empty plastic bottle and your drill, drill a small hole on both sides of the plastic bottle.
3.Pour small fish grains into the bottle,so you should test if food falls out by filling it up, and rotating it while holding it horizontally.
4.connect apparatus accordingly,
  Connect Yellow or data to PIN 9
  Connect Black to GND
  Connect Red to +5V
5.Attach the servomotor to cap with screw.
6.next get your  glue  and glue both the servomotor to  bottle cap, to avoid leakage.
7.After connections,connect arduino cable to computer.
8.Run the code in ARDUINO IDE and observe whether the bottle moves horizontally.

STEPS:
1.Write the code in arduino IDE.
2.Set timer in code without using extra timer.
3.Save the code,go to tools,select board "arduino uno",arduino AVI board,arduino uno

CODE:
#include <Servo.h>  // Include the Servo library to control the servo motor

Servo myservo;  // Create a Servo object named "myservo"

int pos = 0;  // Initialize a variable to store the servo position

long FISHFEEDER = 5000; // Set the feeding interval to 5000 milliseconds (5 seconds)

long endtime;  // Initialize a variable to store the end time of the feeding interval
long now;      // Initialize a variable to store the current time

void setup()
{
  myservo.attach(7); // Attach the servo to digital pin 7
  myservo.write(0);  // Move the servo to the initial position (closed)
  delay(15);         // Wait for the servo to reach the initial position
}

void loop()
{
  now = millis();    // Get the current time in milliseconds
  endtime = now + FISHFEEDER; // Calculate the end time for the feeding interval

  while (now < endtime)
  {
    myservo.write(0); // Keep the servo closed (no food released)
    delay(2000);      // Wait for 2 seconds
    now = millis();   // Update the current time
  }

  // Dispense food by opening the servo gradually
  for (pos = 0; pos < 180; pos += 1)
  {
    myservo.write(pos); // Move the servo to the specified angle
    delay(15);          // Wait for a short time before the next angle
  }

  // Close the servo gradually to the initial position
  for (pos = 180; pos >= 1; pos -= 1)
  {
    myservo.write(pos); // Move the servo to the specified angle
    delay(15);          // Wait for a short time before the next angle
  }
}
OUTPUT:The servo motor will open to dispense food for 2 seconds whenever the specified feeding interval has passed. 

APPLICATIONS:
1.Home Aquariums
2.Large-scale Aquaculture
3.Educational Settings
4.Aquarium Shops and Pet Stores
5.Ornamental Ponds

ADVANTAGES OF FISH FEEDER:
1.For busy aqua farmers, an automatic feeder saves time and effort that would otherwise be spent on daily feedings.
2.Especially for aqua,You don't need to manually feed the fish every day, especially if you're away from home for an extended period. 
3.You can control the amount of food dispensed in each feeding cycle, which helps prevent overfeeding. 

DISADVANTAGES OF FISH FEEDER:
1. Building or purchasing an automatic fish feeder involves an initial investment in terms of time, money, and effort
2.It's going to run out of food after about two or three weeks and you're going to need to restock it.
3.Building and setting up an automatic fish feeder requires some technical skills. You need to be familiar with programming, electronics, and mechanics.


ARDUINO UNO:
Arduino Uno can be used for a wide range of applications, including robotics, home automation, sensor-based projects, data logging, interactive installations, 
educational tools, for small projects.
It contains 
14 digital pins
8 analog pins
AtMega 328 microcontroller
DC supply
USB connection
reset button

SERVOMOTOR:
motor used to rotate w.r/t time in different degrees may as clockwiseand anticlock wise.mainly to control position of object.

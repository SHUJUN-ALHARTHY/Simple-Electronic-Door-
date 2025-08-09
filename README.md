# Simple-Electronic-Door-
In this project, I used a servo motor to control the opening and closing of a simple electronic door instead of a Stepper motor because it was not available to me in Tinkercad.
A push button is used to change the door state: when pressed, the servo rotates to 90 degrees (door opens), and when released, it returns to 0 degrees (door closes).
The internal pull-up resistor was used to stabilize the button reading.
Advantages:
Easy to implement
Low cost
Precise control
Low power consumption
Disadvantages
Limited movement
Limited torque
Limited scalability:

#include <Servo.h>

Servo myservo;             
const int buttonPin = 2;   
int buttonState = 0;       

void setup() {
  myservo.attach(9);       
  pinMode(buttonPin, INPUT_PULLUP);  
}

void loop() {
  buttonState = digitalRead(buttonPin);
  if (buttonState == LOW) { 
    myservo.write(90);       
  } else {
    myservo.write(0);       
  }
  delay(50);                 
}

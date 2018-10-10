# Useless Box

## 3D Printing

**a. Include a photo of your printed part here.**

![alt text](https://github.com/PGhzhang/IDD-Fa18-Lab5/blob/master/IMG_6419.jpg)

**b. Include `.stl` or `.svg` files for your bopper, if 3d-printing.**

## Laser Cutting

**b. Include a photo of your box here.**
![alt text](https://github.com/PGhzhang/IDD-Fa18-Lab5/blob/master/IMG_6420.jpg)

## Electronics

**c. Upload code & a photo of your electronic circuit here.**
![alt text](https://github.com/PGhzhang/IDD-Fa18-Lab5/blob/master/IMG_6421.jpg)


## Putting it All Together

Include here:

1. Your Arduino code.

```
#include <Servo.h> 

#define servoPin  10
#define switchPin 2

#define closePos  0
#define openPos   100

Servo servo;
int switchState;
int previousSwitchState;

// call this when the input on pin 2 changes (LOW to HIGH *or* HIGH to LOW)
void ToggleSwitch(int switchState)
{    
  if (switchState == HIGH)
  {
    servo.write(openPos);
    Serial.println("switch state is HIGH.  servo.write(openPos) called to open useless box");
  }
  else
  {
    servo.write(closePos);
    Serial.println("switch state is LOW.   servo.write(closePos) called to close useless box");
  }
  previousSwitchState = switchState;  // remember that the switch state has changed 
}

void setup()
{
  Serial.begin(9600);
  Serial.println("Useless Box Lab 5");

  // start with the box closed and the switch in the off postion
  switchState = LOW;
  previousSwitchState = LOW;

  // connect to our servo and make sure it is in the closed position
  servo.attach(servoPin);
  servo.write(closePos);

  // we should probably pay attention to the switch
  pinMode(switchPin, INPUT); 
}

void loop()
{ 
  int switchState = digitalRead(switchPin);
  if (switchState != previousSwitchState)
    ToggleSwitch(switchState);

  delay(20);
}
```

2. `.stl` or `.svg` files for your "bopper" — if you use some other technique, include the respective supporting material.

(I drawed the boppr on the computer in MakerLab so I didn't have the file. Some designs of the arm are shown in the picture below. )


3. At least one photo of your useless box taken in the MakerLab's Portable Photo Studio (or somewhere else, but of similar quality).

![alt text](https://github.com/PGhzhang/IDD-Fa18-Lab5/blob/master/IMG_6422.jpg)

4. A video of your useless box in action.

My final product SORT OF works. At first, I placed my servo on the bottom of the box and tried to make a L shape bopper. My strategy was to make the bopper rotate 120 degress and hit the switch. However, the problem I ran into is that the bopper is too weak to push the switch. I started with cardboard and then moved to acrylic. I aslo tried different designs of the bopper but none of them worked out perfectly. Since I didn't really know how to draw shapes in illustrator, it was hard to make the ideal bopper. I made it to work ultimately by elongating the switch. The idea is that the longer the arm of force, the smaller the force. I filmed a video of the bopper pushing the switch back after user pushing the switch. But my bopper is too large to fit in the box though. I think the hardest part of this project is to design the bopper which requires mechanical engineering knowledge. 

Some of the hoppers I tried:

![alt text](https://github.com/PGhzhang/IDD-Fa18-Lab5/blob/master/IMG_6422.jpg)

Final Video:

[![](http://img.youtube.com/vi/qv9gfwHfDpk/0.jpg)](http://www.youtube.com/watch?v=qv9gfwHfDpk "")

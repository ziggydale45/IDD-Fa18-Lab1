# IDD-Fa18-Lab1: Blink!

**A lab report by Jesse Wayne**



## Part A. Set Up a Breadboard

![insert a photo of your breadboard setup here](https://github.com/ziggydale45/IDD-Fa18-Lab1/blob/master/IMG_0310.JPG)


## Part B. Manually Blink a LED

**a. What color stripes are on a 100 Ohm resistor?**
I used a 270 ohm resistor -- looks like red, purple, black, black, brown (though the internet says it should be red, purple, brown, gold)
 
**b. What do you have to do to light your LED?**
Make sure my button is pushed in all the way! I didn't have full contact


## Part C. Blink a LED using Arduino

### 1. Blink the on-board LED

**a. What line(s) of code do you need to change to make the LED blink (like, at all)?**
Change `<pinMode(LED_BUILTIN, OUTPUT);>`, `<digitalWrite(9, HIGH);>`, and  `<digitalWrite(9, LOW);>` to `<pinMode(9, OUTPUT);>` etc.

**b. What line(s) of code do you need to change to change the rate of blinking?**
`<delay(1000);>`

**c. What circuit element would you want to add to protect the board and external LED?**
A resistor
 
**d. At what delay can you no longer *perceive* the LED blinking? How can you prove to yourself that it is, in fact, still blinking?**
I changed my LED from 1000, to 100, to 10 and could no longer see it blinking. I could prove to myself that it's still blinking by slowing the rate by 1 until I can detect it blinking

**e. Modify the code to make your LED blink your way. Save your new blink code to your lab 1 repository, with a link on the README.md.**

```// the setup function runs once when you press reset or power the board
void setup() {
  // initialize digital pin LED_BUILTIN as an output.
  pinMode(9, OUTPUT);
}

// the loop function runs over and over again forever
void loop() {
  digitalWrite(9, HIGH);   // turn the LED on (HIGH is the voltage level)
  delay(2000);                       // wait for a second
  digitalWrite(9, LOW);    // turn the LED off by making the voltage LOW
  delay(2000);                       // wait for a second
}
```


### 2. Blink your LED

**Make a video of your LED blinking, and add it to your lab submission.**

https://youtu.be/lHnSWTakOko


## Part D. Manually fade an LED

**a. Are you able to get the LED to glow the whole turning range of the potentiometer? Why or why not?**
It looks as though my light does change for the whole range of the potentiometer.  I'm using a 270 Ohm resistor + my 10k Ohm potentiometer. This means my range is from 270 Ohm to 10270 Ohm. For the LED to not detectably change throughout the range of the potentiometer, the voltage must either hit a max or minimum threshold, where the LED is powered off or lit as brightly as it can be. My guess is that with different resistor values, I might be able to find this threshold.


## Part E. Fade an LED using Arduino

**a. What do you have to modify to make the code control the circuit you've built on your breadboard?**
I changed

```*/

int led = 9;           // the PWM pin the LED is attached to
int brightness = 0;    // how bright the LED is
int fadeAmount = 5;    // how many points to fade the LED by
```

to 

```*/

int led = 11;           // the PWM pin the LED is attached to
int brightness = 0;    // how bright the LED is
int fadeAmount = 5;    // how many points to fade the LED by
```


**b. What is analogWrite()? How is that different than digitalWrite()?**
 AnalogWrite() will accept a value anywhere between 0 and 255, which is what allows me to Fade the LED with the Arduino. AnalogWrite() will only accept Low or High, which corresponds to on or off.


## Part F. FRANKENLIGHT!!!

### 1. Take apart your electronic device, and draw a schematic of what is inside.
![diagram](https://github.com/ziggydale45/IDD-Fa18-Lab1/blob/master/IMG_0311.JPG)

**a. Is there computation in your device? Where is it? What do you think is happening inside the "computer?"**
This device is a calculator, so there's likely a very basic computer for simple math.

**b. Are there sensors on your device? How do they work? How is the sensed information conveyed to other portions of the device?**

The sensors are on the front side of the device (picture in part 3), where the calculator buttons make contact with the board. Information is conveyed via the boards circuit, which is indicated by the green lines. 

**c. How is the device powered? Is there any transformation or regulation of the power? How is that done? What voltages are used throughout the system?**

The device is powered by a battery. There does not appear to be any transformation or regulation. Neither the board nor the battery indicate voltage, so I'm unsure what voltage is used throughout the system. 

**d. Is information stored in your device? Where? How?**
Information is likely stored at the central black button on my board, as all the circuits land at this button. 


### 2. Using your schematic, figure out where a good point would be to hijack your device and implant an LED.

My Frankenlight has a clearly labeled + and - near the battery. Unfortunately, the calculator didn't work, so I wasn't able to get the LED to light up. I was able to get the Frankenlight to light up on a different device (a microphone).

### 3. Build your light!

**Make a video showing off your Frankenlight.**

![Frankenlight Front](https://github.com/ziggydale45/IDD-Fa18-Lab1/blob/master/IMG_0306.JPG)
![Frankenlight back (sensors)](https://github.com/ziggydale45/IDD-Fa18-Lab1/blob/master/IMG_0307.JPG)
![Frankenlight doesn't work](https://github.com/ziggydale45/IDD-Fa18-Lab1/blob/master/IMG_0308.JPG)
![Frankenlight working (on different device](https://github.com/ziggydale45/IDD-Fa18-Lab1/blob/master/IMG_0309.JPG)

**Include any schematics or photos in your lab write-up.**

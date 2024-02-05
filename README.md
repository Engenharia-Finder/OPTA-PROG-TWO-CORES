# Overview
This programming aims to use the two OPTA cores programmed independently to perform different functions.

# Goals
° Learn how to separate and use two different programs on each OPTA core

# THE TUTORIAL STARTS FROM HERE

# 1° STEP
You need to put the schedule below:
#include <Arduino.h>
#include <RPC.h>

void setup() {
  // put your setup code here, to run once:
pinMode(LED_D1,OUTPUT);
bootM4();
}	

void loop() {
  // put your main code here, to run repeatedly:

digitalWrite(LED_D1,HIGH);
delay(100);
digitalWrite(LED_D1,LOW);
delay(100);

}

# 2° STEP
You need to select the settings as shown in the image below:
![image](https://github.com/Engenharia-Finder/OPTA-PROG-TWO-CORES/assets/133161771/184a7a26-b825-44fc-9b98-6119b7f2d57a)

![image](https://github.com/Engenharia-Finder/OPTA-PROG-TWO-CORES/assets/133161771/88c368eb-749a-4a3e-9e15-d572f085d0a7)


By selecting these options and pasting the schedule above, it is now possible to download this schedule to OPTA. During the programming download process, the following message will appear on the terminal:
“WARNING: library RPC claims to run on mbed, mbed_portenta, mbed_nicla, mbed_giga architecture(s) and may be incompatible with your current board which runs on mbed_opta architecture(s).”

This message does not indicate any error, but rather indicates that the RPC.h library is responsible for the data exchange path between the OPTA Cores and that some Arduino board architectures are not compatible with this library.
When programming within Void Setup we have the bootM4() function; This function is used to turn on or “wake up” the OPTA M4 core. When the programming is finished downloading, the LED_D1 will be blinking on the M7 core.

# 3° STEP

After downloading, select the options below:

![image](https://github.com/Engenharia-Finder/OPTA-PROG-TWO-CORES/assets/133161771/7276940c-dac3-469d-a70c-cec9fda401b7)


# 4° STEP

Enter the following schedule:

#include <Arduino.h>
#include <RPC.h>

void setup() {
  // put your setup code here, to run once:
pinMode(LED_D3,OUTPUT);
//bootM4();
}

void loop() {
  // put your main code here, to run repeatedly:

digitalWrite(LED_D3,HIGH);
delay(100);
digitalWrite(LED_D3,LOW);
delay(100);

}



Note that the M4 co-processor option was selected and in Void Setup, I disabled the bootM4() function;
In addition, I switched on another LED, in this case LED_D3, so when downloading the programming, LED_D3 will also blink. So we have a processor with one programming and also the other processor with another programming.

Video link that explains how to do this: https://www.youtube.com/watch?v=RhPmdI0OaXs

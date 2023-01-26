---
title: Lab 1 - Artemis Board

---
[Return to Main Page](https://themandrazic.github.io/)

## I. Summary
In this lab, the goal was to start up the RedBoard Artemis Nano with the Arduino IDE to ensure that some of the peripherals were working. I wrote very little code in this lab as the majority of the scripts we ran were from the provided SparkFun examples!

---
## II. Blink Example
In this section, we used the example Arduino "Blink It Up" script to flash the LED on and off at a rate of 1 second. Check out the video below to watch it in action!

<iframe width="560" height="315" src="https://www.youtube.com/embed/30YJfUKDW8M" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

---
## III. Serial In Example
For the next example script, we used the Serial port of the Artemis Nano. In thi script, the user sends information in the Serial port and the Artemis Nano echoes it back as the output. Below is a video demonstrating this along with a one-sided conversation with the Artemis Nano.

<iframe width="560" height="315" src="https://www.youtube.com/embed/_e_Vv3_4G98" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

---
## IV. Analog Read example
In this next example script, we use the ananlogRead script to test the on-board temperature sensor on the Artemis Nano. We can see the console output tells us the temperature and along with this information the onbaord LED gets brighter as the temperature decreases and dimmer as the temperature increases! Check out the below video where I press my finger on and blow into the temperature sensor!

<iframe width="560" height="315" src="https://www.youtube.com/embed/P3S2xOT8AkE" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

---
## V. Microphone Output Example
Next, we tested the onboard microphone with the given example script. As we can see in the video, the current frequency is output and the sensor is surprisingly accurate! Most of the frequencies are within 10Hz.

<iframe width="560" height="315" src="https://www.youtube.com/embed/t0PWzByjYfM" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

---
### VI. Detect A Note Challenge
For the final step in this lab, I was tasked with turning the LED on whenever an A note was played. I chose to detect for A4 which is 440Hz. In order to do this, I had to add two snippets of code. The first snippet was to configure the LED which I took from the "Blink It Up" example script in section **II**. Here is the code that was added to the setup() block:
```C
// initialize digital pin LED_BUILTIN as an output.
  pinMode(LED_BUILTIN, OUTPUT);
```
The next piece of code I wrote was the logic to turn the LED on whenever 440Hz was detected. Due to the slight microphone inaccuracies we saw in section V, I added some room for error. This logic was put into the loop() block:
```C
// Turn on the LED if the frequency is A440
  if (ui32LoudestFrequency > 435 && ui32LoudestFrequency < 450)
  {
    digitalWrite(LED_BUILTIN, HIGH);  // turn the LED on (HIGH is the voltage level)
  }
  else
  {
    digitalWrite(LED_BUILTIN, LOW);   // turn the LED off by making the voltage LOW
  }
```

To below video showcases the full working system!

<iframe width="560" height="315" src="https://www.youtube.com/embed/kWITh8WR3sY" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

### VII. Wrap-Up
Overall this lab was a great introduction to using the RedBoard Artemis Nano and I'm excited for what's to come!
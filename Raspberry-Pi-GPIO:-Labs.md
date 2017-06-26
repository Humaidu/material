# ![Raspberry Pi GPIO: Labs](../blob/master/assets/img/logo-128.png?raw=true)

Welcome to the GPIO lab! This time, we're going to build a couple of circuits using the Rapsberry Pi. Grab your breadboard and a couple of cables.

## Prep

Take one cable and connect it to the +5v GPIO pin - those are on the top right as you look at the pins. Connect the other end of the cable to one of the positive rails on the breadboard - near the red line.

Take another cable and connect one of the GPIO Ground pins ("GND") to one of the negative rails on the breadboard - near the blue line.

![RPi GPIO Pinout](https://sensorgnome.org/@api/deki/files/14074/=RPi2_Pinout.png)

![breadboard](https://cdn-learn.adafruit.com/assets/assets/000/002/602/medium800/learn_arduino_breadboard_half.jpg)

## Code

Let's write some python! You should have the python `gpiozero` package installed (`pip list` to check). If you don't, `sudo pip install gpiozero`

```python
foo = "bar"
```
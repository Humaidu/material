Again, 9am start. Wanted to start with the big reveal of electronics on Monday morning but rain on Sunday night, and then Monday night! So I just bought the kit to class and handed it out 1 between 2.

Talked through the electronic components - a first for many in the class - then we made the circuit on the breadboard from +5v through the LED and resistor to ground on the Pi. Simple stuff.

Then connected +ve end of the LED to GPIO pin 17, giving an opportunity to show the pi pinout & discuss the nature of some of the pins.

Had the LED flash in code, we all went through it at the same time for the LED moment. Success!

Then had the class write a dash and dot function then write out their name in morse code. Still, many had trouble with the idea of writing a function and then calling it, so I went through it individually with some pairs. All got it eventually.

Next up, I handed out buttons and set them off on the button lab, which took us through to lunch.

This afternoon we'll have it so that when you push a button it'll flash out your name - so code reuse. then maybe some fun stuff like having it reset your computer. Finally we'll walk through IFTTT - build a recipe so you get an email when you push a button. Fab!

Tomorrow we'll do some MQTT stuff, then we can build a button on their webpage that'll flash a light on their computers. I'll need to write that lab tonight.

After lunch we came straight back into my dreamed-up "say my name" lab - to spell out the letters of your name in morse code. This is a really nice opportunity to talk about abstraction - I have led.on() and off(), then on top of that I have a function called dot() and dash(), then functions that use those called A(), B(), C() etc. layers of abstraction so my API is cleaner and nicer to use.

Next up, the "turn my button into a reset switch for the pi" lab, which is just a bit of fun. 2:30 we'll go to IFTTT then run with that for the rest of the day.
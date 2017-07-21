Last teaching day and we're finishing with Web APIs and some Hard Challenges.

Skipped through the web APIs stuff, didn't use the slides. I've decided I don't even like the slide format, writing code in walkthroughs is much more fun. We talked about what an API is - and the ones we've used in the past. Local objects and even, kind of, our MQTT flashing lights. So we did the pyowm then investigated using it with a few questions - what's the temperature at the highest city in the world? Encourages students to solve two problems - use google.

Then we talked about layered APIs - how we built up our LED examples in layers - led.on() and led.off(). Then dot() and dash(). The S(), A(), M(). So we're more abstracted away from the work of switching lights on and off, but it's still happening. And we're in a nicer world, much closer to our problem domain.

So then we discussed structured data - how OWM might actually work as a network of sensors located around the world. What data do the sensors pass? "Cloudy". 90. 280. The difference between data and informtion - what do those facts mean? Okay, Status: Cloudy, Humidity: 90, Temperature: 280. But *where* is that data coming from? (Status, Koforidua): Cloudy. And *when*?? etc etc.

Then we'd talked about layered APIs and how this data is coming across the web, so we looked at the actual requests. Allowed us to talk about JSON & tie that back to the key/value discussion we'd just had.

Left the students with that API and newsapi.org for a while, then laid down the challenge: "Print out all the headlines from newsweek" with no help. Well, a little bit.

--

1:30 - students are having trouble with the question - I've pointed them to the slide material for dictionary and for loops, so hopefully that'll work. I think the task here is just to keep checking they're working the problem.

Problem solving is a huge deal, and it's just not here. John Latham really did great work for us at Manchester, I should thank him.
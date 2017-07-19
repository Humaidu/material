great start to the morning - MQTT!

Started with a discussion of client/server pub-sub systems, messages, topics, subscriptions etc.

Then had the class subscribe with

mosquitto_sub -t test/all -h moorhouseassociates.com

where I had an mqtt server running in docker. I published a messge in a a hidden terminal with

mosquitto_pub -t test/all -h moorhouseassociates.com -m "Hello Class!"

then discussed how we can make a chat system by subscribing to more than one topic - one for the room and one for our own name. Revealed the publish command and let the class play with messages. Left my terminal with the subscription to test/all on the projector for fun and read out some of the cleaner messages.

Then we wrote the python class together, which was great fun. Had another chance to talk about callback functions, and why we need loop_forever or else the code would just exit. Also spent some time discussing port numbers and why we use timeouts in distributed systems, different failure modes and all that.

Left the class to make it so their LEDs light when they get a message over MQTT until lunch.

After lunch we'll build MQTT on the web, and spend some more time flashing lights etc.
# ![Distributed Systems: Labs](../blob/master/assets/img/GC_Logo_artwork_RGB-LOGO_colour_SMALL.png?raw=true) 

Welcome to the Distributed Systems lab! This time, we're going to learn about MQTT, then build on top of everything we've learned to build a connected web application.

## Intro

MQTT is a messaging protocol specifically designed for small, distributed systems of sensors and actuators. That means it's great for us to use!

There are great Python MQTT libraries; the one we're going to be using is called [mosquitto](https://www.mosquitto.org/). Head over there and read about it.

You should already have mosquitto installed, but if you haven't, run the following command in a Terminal (`ctrl`+`alt`+`t`)

    sudo apt-get install mosquitto mosquitto-clients

### Basics

You can use MQTT to send and receive a _payload_ of data. Right now, we're going to practice using a really simple example: we're going to chat to each other! Enter the following command:

    mosquitto_sub -t glblcd/chat -h <hostname>

### Chat

Now, open _another_ Terminal window (`ctrl`+`alt`+`t`!) and run this command once:

    mosquitto_pub -t glblcd/chat -h <hostname> -m "Hello, my name is ..."

Everyone else is the class can see your message! Write something to your friend.

### Channels

The `-t` switch sets the topic on which the message is sent. Experiment with sending messages on different channels. Find out how to subscribe to messages on multiple channels so you can listen to messages on a chat room for your university, and one for private messages.

## Python

Investigate the mosquitto Python library. Use it to build a chat application in code.

Extend your GPIO work to send messages to a friend using mosquitto.

E.g.:

https://devcenter.heroku.com/articles/cloudmqtt#using-with-python
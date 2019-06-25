# ![MQTT with Python & Pi: Labs](../blob/master/assets/img/GC_Logo_artwork_RGB-LOGO_colour_SMALL.png?raw=true) 

In this lab, we're going to investigate [paho-mqtt](https://pypi.org/project/paho-mqtt/), a python library for MQTT.

## Introduction
MQTT is a pub/sub framework for sending small messages between IoT devices. We've got an MQTT server set up which you can connect to for the rest of the program. If you like, you can set up a free MQTT server on your Heroku account: [[https://devcenter.heroku.com/articles/cloudmqtt]].

## Getting started
Make sure you've got paho-mqtt installed:

    pip install paho-mqtt

## Code

First, import the library and alias it to ```mqtt```:

```python
import paho.mqtt.client as mqtt
```

Next, we define two functions. These will be called by ```paho``` when the connection has been successfully made, and every time a message arrives:

```python
def on_connect(client, userdata, flags, rc):
    print("Connected with result code "+str(rc))

    # Here you can subscribe to whatever topics you like
    # use '#' for a 'wildcard' - subscribe to any messages
    client.subscribe("glblcd/sam")
    
```

The ```on_message``` callback is called with the message object which contains ```payload``` - a string containing the message content. This could be plain text, xml, or json - whatever the sender has sent

```python
def on_message(client, userdata, msg):
    print(msg.topic+" "+str(msg.payload))
```

Next, we instantiate the MQTT client object and set up the callbacks

```python
client = mqtt.Client()
client.on_connect = on_connect
client.on_message = on_message
```

Once this is done, we can attempt to connect to the server. Your teachers will provide the hostname for this class.

```python
client.connect("globalcode.org.uk", 1883, 60)
```

Finally, we prevent the program from exiting by calling ```loop_forever```. This allows incoming messages to be handled. You can hit ```Ctrl-C``` to exit the program.

```python
client.loop_forever()
```
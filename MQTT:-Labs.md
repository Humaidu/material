# ![MQTT with Python & Pi: Labs](../blob/master/assets/img/GC_Logo_artwork_RGB-LOGO_colour_SMALL.png?raw=true) 

In this lab, we're going to investigate [paho-mqtt](https://pypi.org/project/paho-mqtt/), a python library for MQTT.

## Introduction
MQTT is a pub/sub framework for sending small messages between IoT devices. We've got an MQTT server set up which you can connect to for the rest of the program.

If you like, you can set up a free MQTT server on your Heroku account: [[https://devcenter.heroku.com/articles/cloudmqtt]].
Doing so will most likely require you to set up a bunch of passwords, usernames etc, so we'll skip that for today.

## Getting started
Make sure you've got paho-mqtt installed:

    pip3 install paho-mqtt

then make sure you have mosquitto installed on your computer. This little program will start a little message broker on your machine. the 2 pieces of code we write below will connect to it later.

    sudo apt-get install mosquitto mosquitto-clients

## Code
We're going to run 2 bits of code at the same time. One one end you'll have a terminal window later that receives the messages from the mqtt server and in an other window we'll send messages to the server.

We could have done both in the same window, but You'd end up receiving messages while trying to type, which is messy ;)

### Reading messages
create a new directory called `mosquitto` in your `~/dev` folder. In this folder we'll create a file called `read.py`

open it in your favourite editor and import the library we pip installed earlier and alias it to ```mqtt```:

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
    print(msg.topic + " \n " + msg.payload.decode("utf-8") + " \n ")
```

Next, we instantiate the MQTT client object and set up the callbacks

```python
client = mqtt.Client()
client.on_connect = on_connect
client.on_message = on_message
```

Once this is done, we can attempt to connect to the server. Your teachers will provide the ip address of his/her raspberry pi for the class.

```python
client.connect("192.168.1.x", 1883, 60)
```

Finally, we prevent the program from exiting by calling ```loop_forever```. This allows incoming messages to be handled. You can hit ```Ctrl-C``` to exit the program.

```python
client.loop_forever()
```

you can now execute the file with `python3 read.py`

### Sending messages
So you can now read messages, but none are sent yet! let's fix that.

We'll create a new file called `send.py` and put some sending logic in there.

First of all we need to import `paho`'s client as `mqtt` again

```python
import paho.mqtt.client as mqtt
import time
```

with that done we'll define one function that warns us when we're ready to send messages. In that function we set `Connected` to `True`.

```python
def on_connect(client, userdata, flags, rc):
    if rc == 0:
        print("Connected to broker")
        global Connected  # Use global variable
        Connected = True  # Signal connection

    else:
        print("Connection failed")
```

Then we initialize `Connected` to `False`
```python
Connected = False  # global variable for the state of the connection
```
Then we need to run this function when paho connects, connect to the right server and start the loop:
```python
client = mqtt.Client()
client.on_connect = on_connect
client.connect("192.168.1.x", 1883, 60)
client.loop_start()  # start the loop
```
Then we sleep until it's connected to server:
```python
while Connected != True:  # Wait for connection
    time.sleep(0.1)
```

Now we just need to have a while loop waiting for user input and send the message, remember to disconnect and stop the client loop when the program is interrupted.
```python
try:
    while True:
        message = input('Your message: ')
        client.publish("glblcd/sam", message)

except KeyboardInterrupt:
    client.disconnect()
    client.loop_stop()
```


you can now run `python3 send.py` and send messages!

## Exercises
Work in pairs or groups, go back to your MQTT labs and refactor them to respond to messages over MQTT.

You could try to automatically respond to messages (if they contain content) and build a personal assistant, change the colour of the text, etc.

Make sure to create a new git repository from this code and push it up!
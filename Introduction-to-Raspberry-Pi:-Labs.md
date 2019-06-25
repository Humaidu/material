# ![Intro to Python: Labs](../blob/master/assets/img/GC_Logo_artwork_RGB-LOGO_colour_SMALL.png?raw=true) 

Welcome to the Raspberry Pi lab!

Work through this lab on your own or with friends. We'll do the first few topics together, then you're free to have a play around on your own!

## Set up your Raspberry Pi
Push the SD card firmly into your Raspberry Pi. Plug the Keyboard and Mouse into the USB ports on the side, and plug in the screen using the HDMI cable that comes with it.

Finally, using the cable that comes with your Pi, plug it in! Check you can see the green light on the board, and you should see the Raspberry Pi logo on the screen. 

## Install

First, check you're connected to the internet!

Before we really get started, there's two things we need to do together. Use the mouse to click the raspberry icon in the top-left corner of the screen, then find the Terminal in the Accessories menu.

Then enter these commands:

    sudo apt-get update
    sudo apt-get -y upgrade
    sudo apt-get -y install rpi-update
    sudo rpi-update
    sudo shutdown -r now

Some of them might take quite a while - we're downloading the latest version of the Raspbian OS, so you have all the latest patches.

## Setup

Once your raspberry pi has rebooted, re-open the Terminal app. Use the `whoami` command to find out your username - what is it?

The Raspberry Pi comes with a default user called *pi*, who has the password *raspberry*. Let's add a new user and do some setup. Enter the following commands, replacing "\<username\>" with a username you want to use. Try your first name!

    sudo adduser <username>
    sudo usermod -a -G adm,dialout,cdrom,sudo,audio,video,plugdev,games,users,input,netdev,spi,i2c,gpio <username>

These commands will ask you for a new password, along with some other details. Choose something only you know, that you can remember easily!

Now, from the Applications menu, find *Raspberry Pi Configuration* under *Preferences*. Uncheck the box next to "Login as user 'pi'". This means you'll now have to enter your username and password whenever you want to login to your Pi. You'll also now have to enter your password whenever you use the "sudo" command :)

Reboot your Pi and login, using your new account. Now we need to remove the default "pi" account. Open the Terminal again, and enter the following command:

    sudo userdel -r pi

This has deleted the original default user. Now someone needs to know your password before they can login!

Finally, let's create the directory that you'll be doing most of your work in:

    mkdir dev

Now, we're done!

## Discover

Find out:
* What does `sudo` do? Type `man sudo` in a terminal window to read the *manual* page for the sudo command.
* How do I add another desktop?
* In the `terminal`, what does the command `pwd` do?
    * What does `cd` do? What about `ls`?

## Play

Go ahead and play around - it's your computer now! Try these things:
* Change the background image to something you like. There's a bunch of great hi-res photography at [UnSplash](https://unsplash.com) and [Pexels](https://www.pexels.com/) :)
* Change the appearance settings
* Change the shortcuts in the application launch bar - I prefer the "Chromium Web Browser", for example.
* Check your email and join our slack channel!

## Install

When you get a moment, please install the following pieces of software:

postgresql, a database:

    sudo apt-get install postgresql

Ninja, an IDE:

    sudo apt-get install ninja-ide

Mosquitto, an MQTT client we'll be using next week:

    sudo apt-get install mosquitto mosquitto-clients

Docker, a toolkit for running applications in isolation:

    curl -sSL https://get.docker.com | sh

Arduino, the toolkit for our arduino devices:

    sudo apt-get update && sudo apt-get install arduino

## I'm brave!
If you're really brave, or you've used linux before, why not install a different distro? There's a bunch available [here](https://www.raspberrypi.org/downloads/).

If you know a bit of Python already, why not explore the GPIO pins on your Raspberry Pi? We'll get there next week but feel free to look ahead: details [here](https://www.raspberrypi.org/blog/gpio-zero-a-friendly-python-api-for-physical-computing/)

## Next
Next, we need to learn linux. Follow the [[Linux labs|Introduction-to-Linux:-Labs]] next!
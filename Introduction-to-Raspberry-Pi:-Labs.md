# ![Intro to Python: Labs](../blob/master/assets/img/logo-128.png?raw=true)

Welcome to the Raspberry Pi lab!

Work through this lab on your own or with friends. We'll do the first few topics together, then you're free to have a play around on your own!

## Set up your Raspberry Pi
Push the SD card firmly into your Raspberry Pi. Plug the Keyboard and Mouse into the USB ports on the side, and plug in the screen using the HDMI cable that comes with it.

Finally, using the cable that comes with your Pi, plug it in! Check you can see the green light on the board, and you should see the Raspberry Pi logo on the screen. 

## Install Raspbian
*Raspbian* is the name of the Operating System that comes free with the Raspberry Pi. It includes a GUI, which we'll use the most. It also comes with a powerful commandline which we'll see, too.

You can install Raspbian by selecting it and clicking the "Install" button at the top of the screen. The installation might take quite a while!

Before we really get started, there's two things we need to do together. Use the mouse to click the raspberry icon in the top-left corner of the screen, then find the Terminal in the Accessories menu.

Then enter these commands:

    sudo apt-get update
    sudo apt-get -y upgrade
    sudo apt-get -y install rpi-update
    sudo rpi-update
    sudo shutdown -r now

## Setup

Once your raspberry pi has rebooted, re-open the Terminal app. Use the `whoami` command to find out your username - what is it?

The Raspberry Pi comes with a default user called *pi*, who has the password *raspberry*. Let's add a new user and do some setup. Enter the following commands, replacing "<username>" with a username you want to use. Try your first name!

    sudo adduser <username>
    sudo adduser <username> sudo

These commands will ask you for a new password. Choose something only you know, that you can remember easily!

Now, from the Applications menu, find *Raspberry Pi Configuration* under *Preferences*. Uncheck the box next to "Login as user 'pi'". This means you'll now have to enter your username and password whenever you want to login to your Pi. You'll also now have to enter your password whenever you use the "sudo" command :)

Reboot your Pi and login, using your new account. Now we need to remove the default "pi" account. Open the Terminal again, and enter the following command:

    sudo userdel -r pi

This has deleted the original default user. Now someone needs to know your password before they can login.

## Discover

Find out:
* what does `sudo` do? Type `man sudo` in a terminal window to read the *manual* page for the sudo command.

## Play

Go ahead and play around - it's your computer now! Try these things:
* Change the background image to something you like
* Change the appearance settings
* Change the shortcuts in the application launch bar - I prefer the "Chromium Web Browser", for example.
* Browse to https://iotinafrica.slack.com/ & join our #koforidua2017 channel
    * Make sure to save a bookmark
    * Say hi
    * Install it on your phone, too - chat from anywhere!
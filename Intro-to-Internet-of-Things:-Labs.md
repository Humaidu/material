
Welcome to the IoT lab! This time, we're going to be using If This Then That ([IFTTT](https://ifttt.com/)) to build some complex systems on the internet.

## Intro

Firstly, head over to [IFTTT](https://ifttt.com/) and create an account. If you've got a cellphone that supports it, install the IFTTT app, and sign in there as well.

## Basics

Investigate some basic IFTTT recipes. Read about _applets_ and _services_ on the [about](https://ifttt.com/about) page. Create some simple recipes: here are some fun examples:

* [Cold tomorrow? Notify me!](https://ifttt.com/applets/56473384d-cold-tomorrow-notify-me)
* [Post a thankyou to a new twitter follower](https://ifttt.com/applets/Sf9CXKg7-new-follower-post-thank-you-tweet)
* [Cool new desktop wallpapers](https://ifttt.com/applets/81720p-email-me-3840x1080-wallpapers-from-r-wallpaper-reddit)
* [Find my phone!](https://ifttt.com/applets/68196p-finding-my-phone-when-it-s-lost)

Here are some more funny recipes:
* [Mashable](http://mashable.com/2013/03/22/funny-ifttt-recipes)

## Maker Webhook

Let's investigate the [GPIO Mobile Notification](https://ifttt.com/applets/351412p-gpio-mobile-notification). This applet sends you a cellphone notification every time a certain URL is accessed. We can use the python `requests` library to do this every time your button is pressed.

To start with, install the applet and test it out. Browse to your "maker webhooks" settings and find your account URL. Browse to the URL and test out the connection with some sample data - you should get a notification on your phone!

## Back to Python
Now, you can use the `requests` library to access that URL from python!

    pip install requests

Then, in the Python REPL:

```python
r = requests.get(<the url>)
```

Again - you should get a notification on your phone! If you don't, check the value of `r.status_code` - it should be '200'

## GPIO
This part is fun - remember how to add an event handler to your button in Python? Write some code so that when you press the button, you get a notification on your phone!

Try to send a fun message to yourself, 
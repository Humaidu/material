# ![Hosting Platforms: Labs](../blob/master/assets/img/GC_Logo_artwork_RGB-LOGO_colour_SMALL.png?raw=true) 

In this lab, we're going to investigate [Heroku](https://www.heroku.com/). Head over there and sign up for an account - it's free!

## Intro
Remember your web server from the other day? We're now going to host it on the internet so you can browse to it. If you want to make changes to your website, you'll use the following flow:

* Sync your local dev environment to your website's github repo
* Make your changes locally & commit them
* Push your changes to github
* Heroku sees that your github repo has changed & syncs the changes
* Heroku restarts your dyno

This means you'll be able to see changes you make to your website in just a few seconds!

## Getting started
Let's go back to your Web Application's project directory. To host your web app on Heroku, we'll need two extra files:

### requirements.txt
`requirements.txt` is used by `pip` to automatically install all the python modules you need on Heroku. Your app probably only uses flask:

    Flask==1.1.1

### Procfile
`Procfile` tells Heroku what to do when it starts up. Your `Procfile` should contain just one line (watch out, this filename begins with an upercase `P`):

    web: python myapp.py

## Check it in
Make sure to commit your two new files, and any other changes you've made - and then push them to github with `git push`

## Create the Heroku app
Login to your Heroku dashboard, and create a new app. Give it a unique name, and place it in Europe.

## Link the app to Github
In your app's _deploy_ settings, choose the _Github_ deployment method. Type your repo's name in the box and hit 'Search'. Find the right repo and hit 'connect'

## Enable automatic deploys
Next, scroll down and enable automatic deploys for your project. This means that whenever you make a change to your repo on Github, Heroku will attempt to grab the changes and publish them to the web.

## Deploy once
Finally, scroll down to the bottom of the page and hit the "Deploy" button. This does a first-time deploy of the code in your github repo.

This might take some time, but you can watch the activity in the log output on the screen. If there are any problems with your setup, this is where they'll appear.

## Go see!
Hit the "Open App" button at the top of the screen to browse to your website. Tell your family and friends!
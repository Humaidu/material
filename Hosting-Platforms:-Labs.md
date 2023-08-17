# ![Hosting Platforms: Labs](../blob/master/assets/img/GC_Logo_artwork_RGB-LOGO_colour_SMALL.png?raw=true) 

In this lab, we're going to investigate [Render](https://render.com/) Head over there and sign up for an account - it's free!

## Intro
Remember your web server from the other day? We're now going to host it on the internet so you can browse to it. If you want to make changes to your website, you'll use the following flow:

* Sync your local dev environment to your website's github repo
* Make your changes locally & commit them
* Push your changes to github
* Render sees that your github repo has changed & syncs the changes
* Render restarts your dyno

This means you'll be able to see changes you make to your website in just a few seconds!

## Getting started
Let's go back to your Web Application's project directory. To host your web app on Render, we'll need an extra file:

### requirements.txt
`requirements.txt` is used by `pip` to automatically install all the python modules you need on Heroku. Your app probably only uses flask:

    gunicorn==21.2.0
    Flask==2.5.5


## Check it in
Make sure to commit your new file, and any other changes you've made - and then push them to github with `git push`

## Create the Render app
* Login to your Render dashboard 
* create a new app by clicking on the new button and select web service
* Give Render permission to access your github repos and select the one you want to deploy by clicking on the connect button
* Give it a unique name
* click on Create Web Service to deploy your application.

## Go see!
Hit the application link at the top left corner of the screen to browse to your website. Tell your family and friends!
# ![Hosting Platforms](../blob/master/assets/img/logo-128.png?raw=true)
## Teaching Materials

[Teaching Slides](https://gitpitch.com/iotinafrica/material?p=hosting-platforms)
| [[Labs|hosting-platforms:-labs]]

## Introduction
The aim of this module is to encourage the student to:
* think about operational concerns outside their code
* recognise the dollar cost of running their output
* understand the benefits of externalising assumptions about dependencies

Ultimately, we're introducing the concept of the [12 Factor App](https://12factor.net/) and associated DevOps concerns.

## Length
We encourage a labs-first approach for this course. The lab is entirely operational and can be done in pairs by following a worksheet. Onboarding a simple Python webapp onto Heroku is simple but has a huge payoff, so is a perfect candidate for lab-first.

The taught section of this course shows the motivation for a container system like heroku - and highlights the gap between local development and production deploy. The next step is potentially a discussion for how to bring the 'exposed dependencies' model *back* to the local dev environment - perhaps through something like virtualbox.

## Learning aims
After completion of this course, the student should be able to:
* Describe the differences between development and production environments
* Set up and deploy a Python web application on a hobby Heroku dynamo

## Prerequisites
The student should have completed the Intro to Python course, or similar.
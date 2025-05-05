
# Node.js Hello World - CI/CD with Jenkins

## Overview

This project demonstrates deploying a simple Node js "Hello World" app using Jenkins CI/CD triggered by GitHub webhook.

---

## Features

- Node.js Express app with a single route returning "Hello World"
- Jenkins pipeline set up locally
- Webhook from GitHub triggers Jenkins on every push
- Jenkins pulls latest code, installs dependencies, and restarts the app

---

# TOOLS USED 
- nodejs for creating app 
- jenkins PIPELINE for CICD
- git for version control 
- github and webhooks to trigger jenkins pipeline (AS Codeberg is facing internal server error on creating new account )
- Localtunnel to expose jenkins via public url 

### HOW I SET UP ALL THIS 
# Step 1
- Install node js (i have it already)
- create a working directory (Or open directory with VS Code )
- create app.js file and a readme file 
- run this command :- npm init -y to create default json file 

# Step 2
- write hello world code in app.js (or take help for nodejs code )
- run npm start 
- check for the localhost:3000

# Step 3 
- push code to codeberg (I am pushing on github , issue in reg. an account on codeberg right now )
 - open github repo 
 - Go to settings -> webhooks -> add a webhook 
 - got to setp 4 , then come back 
 - ensure selected "trigger on every push"
 - save the webhook

 # Step 4 
 - run the command below in cmd or terminal
 lt --port 8080 --subdomain customname
 - output looks like 
 your url is: https://shivamjenkins8168.loca.lt

- complete this url by adding /github-webhook/
your url is: https://shivamjenkins8168.loca.lt/github-webhook/
- Now add this in payload url as discussed in  # step 3
- save it 


# Step  5
- create a jenkins job 
- choose free style project as it is simple node js hello world app.
- choose SCM as git and provide URL of github repo 
- add build steps



### REQYUIREMENTS ###
- jenkins SCM Pulls the latest code on every build 
- pkill -f "node app.js" || true -: kills previously runing app 
- nohup npm start & :- restart app 


#####           QUERY                 #####
I am a little bit confused as the assignment says to set up CICD pipeline using Github Actions,
but in the below section requirements , it demands for jenkins.
I am more comfortable using JEnkins so I am using jenkins here.

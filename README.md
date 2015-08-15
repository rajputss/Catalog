# udacity_restaurant_app

Project and Goals
This project is Udacity's Full Stack Nano Degree track's third project. I worked on this project while going through the course following Lorenzo and then built an application that I actually wanted. 

The following instructions assume you have GIT, VirtualBox, and Vagrant installed. Kindly use the links below to download should you need.

VirtualBox Installation- https://www.virtualbox.org/wiki/Downloads Install the platform package for your operating system. You do not need the extension pack or the SDK.

Vagrant Installation - https://www.vagrantup.com/downloads Vagrant is the software that configures the VM and lets you share files between your host computer and the VM's filesystem.

Git Installation - http://git-scm.com/downloads Install the version for your operating system. On Windows Git will provide you with a Unix-style terminal and shell (Git Bash). On Mac or Linux systems you can use the regular terminal program.

Configuration Instructions

This project requires:

    Python Libraries: requests, oauth2client, and httplib2
    Python 2.7
    SQLite
    SQLAlchemy
    Flask 0.10.1

STEPS:

    Using Git, clone this repository to your local machine.
    Using terminal go to your vagrant directory in your recently downloaded repository, type $vagrant up to launch     your virtual machine. It will install all the dependencies and thus will take few moments.
    Once vagrant is up, type $vagrant ssh to log into it. Your terminal will be logged into the virtual machine and     here you will be using Linux shell prompt.
    
    Change to the /vagrant directory by typing cd /vagrant.
    Then change to application folder by typing cd application.
    You can type ls to ensure you are in that folder
    Here you will have to set up database. Follow instructions below for database setup:
        To set up database type $ python database_setup.py
        This will give you an empty database with four tables a. sport b. item c. user d. admin
        Now to populate this empty database type python addstuff.py
        This will add sports categories and items to the database along with an admin user
    
    Now you can run the command python project.py to launch the application
    If the terminal says it can't find some modules then open requirements.txt file to see detailed instructions on     how to install dependencies.
    
    Open your browser to access your local machine @ http://localhost:8000
    You may find list of sports categories and a list of most recent items that were added.
    If you are not logged in using G+ or FB credentials, you can only browse sport categories and view item            descriptions.

    This application uses OAuth provided by G+ and FB, therefore, you may need a connection from each. Below is how you can obtain that connection id.

    For Google G+:
        Go to https://console.developers.google.com
        Create new project and give it a name; like Sports application.
        Don't change the project ID. It could take few moments for it to get your application set up.
        Once ready, you will see APIs & auth on your left panel, go to credentials and click create new client ID.
        For Application type, choose web application then click configure consent screen.
        Assign an email address and enter product name such as Sports Catalog and hit save.
        In the box where it says Authorized JavaScript origins, add http://localhost:8000 then click Create Client         ID.
        Click Download JSON and save the file in the same folder where you have your application saved
        Rename this file to clients_secret.json
        Go to your login.html file => application/templates/login.html
        On line 57, you will find => data-clientid="" //<=YOUR G+ ID GOES HERE enter google client id within ""

    For Facebook:
        Go to https://developers.facebook.com
        Go to MyApps and add a new App.
        You will get a pop window, select Website.
        Enter a name for the app. I like to keep it same thus I used Sports application.
        Choose the best fit category (Sport) and click create App ID.
        For the site URL, enter http://localhost:8000
        Now skip to Developer Dashboard and jot down your app ID and app secret.
        Add your Facebook application ID and secret to the fb_client_secrets.json file. You may find the file in           the same folder your application is saved.
        Go to your login.html file => application/templates/login.html
        On line 120, you will find => appId : "", //<=YOUR FB ID GOES HERE enter facebook id within ""

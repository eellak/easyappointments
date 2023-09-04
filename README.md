<h1 align="center">
    <br>
    <a href="https://easyappointments.org">
        <img src="https://raw.githubusercontent.com/alextselegidis/easyappointments/develop/docs/images/logo.png" alt="Easy!Appointments" width="150">
    </a>
    <br>
    Easy!Appointments
    <br>
</h1>

<br>

<h4 align="center">
    A powerful Open Source Appointment Scheduler that can be installed on your server. 
</h4>

<p align="center">
  <img alt="GitHub" src="https://img.shields.io/github/license/alextselegidis/easyappointments?style=for-the-badge">
  <img alt="GitHub release (latest by date)" src="https://img.shields.io/github/v/release/alextselegidis/easyappointments?style=for-the-badge">
  <img alt="GitHub All Releases" src="https://img.shields.io/github/downloads/alextselegidis/easyappointments/total?style=for-the-badge">
</p>

<p align="center">
  <a href="#about">About</a> •
  <a href="#features">Features</a> •
  <a href="#setup">Setup</a> •
  <a href="#installation">Installation</a> •
  <a href="#license">License</a>
</p>

![screenshot](screenshot.png)

## About

**Easy!Appointments** is a highly customizable web application that allows customers to book appointments with you 
via a sophisticated web interface. Moreover, it provides the ability to sync your data with Google Calendar so you can 
use them with other services. It is an open source project that you can download and install **even for commercial use**. 
Easy!Appointments will run smoothly with your existing website as it can be installed in a single folder of the 
server and of course share an existing database.

## Features

The application is designed to be flexible enough so that it can handle any enterprise work flow. 

* Customers and appointments management.
* Services and providers organization.
* Working plan and booking rules.
* Google Calendar synchronization.
* Email notifications system.
* Self hosted installation.
* Translated user interface.
* User community support. 


### GFOSS Adjustments

We made minimal changes in EASY!APPOINTMENTS source code.

* We added a new css file to change the appearence of the interface. 
* We added the capability to automatically generate a jitsi link if the location field at the service form is empty, stored in the database and send it by email to the user.
* If the Administrator doesn’t set a physical location for a service platform creates a unique Jitsi link using the appointment’s hash
* We used the native location field to store and show the Jitsi link
* We added the location field in the email the user receives
* In Administration Settings we added fields to add / change text in homepage



## Setup

To clone and run this application, you'll need [Git](https://git-scm.com), [Node.js](https://nodejs.org/en/download/) (which comes with [npm](http://npmjs.com)) and [Composer](https://getcomposer.org) installed on your computer. From your command line:

```bash
# Clone this repository
$ git clone git clone https://github.com/eellak/easyappointments.git

# Go into the repository
$ cd easyappointments

# Install dependencies
$ npm install && composer install

# Start the file watcher
$ npm start
```

Note: If you're using Linux Bash for Windows, [see this guide](https://www.howtogeek.com/261575/how-to-run-graphical-linux-desktop-applications-from-windows-10s-bash-shell/) or use `node` from the command prompt.

You can build the files by running `npm run build`. This command will bundle everything to a `build` directory.

## Installation

You will need to perform the following steps to install the application on your server:

* Make sure that your server has Apache/Nginx, PHP and MySQL installed.
* Create a new database (or use an existing one).
* Copy the "easyappointments" source folder on your server.
* Make sure that the "storage" directory is writable.
* Rename the "config-sample.php" file to "config.php" and update its contents based on your environment.
* Open the browser on the Easy!Appointments URL and follow the installation guide.

That's it! You can now use Easy!Appointments at your will.

You will find the latest release at [easyappointments.org](https://easyappointments.org).
If you have problems installing or configuring the application visit the
[official support group](https://groups.google.com/forum/#!forum/easy-appointments).
You can also report problems on the [issues page](https://github.com/alextselegidis/easyappointments/issues)
and help the development progress.


### GFOSS adjustments

In order Easy!Appointments to work with your jitsi server we changed: 

* in our config-sample.php you must set the JITSI_URL variable to your server's jitsi URL, ex.: https://jitsi.example.com/
* Added two fields in the database:
INSERT INTO `bookingjitsiwp`.`ea_settings` (`name`, `value`) VALUES ('display_landing_page', '1');
INSERT INTO `bookingjitsiwp`.`ea_settings` (`name`, `value`) VALUES ('landing_page_content', 'I am the Landing Page Content ');
* In file engine/Notifications/Email.php we added appointment location with the jitsi link.
* In file application/views/emails/appointment_details.php we show the link with the location data.
* Changed the following javascript files to show an html editor and receive the values:
/assets/js/backend_settings.min.js
/assets/js/backend_settings_system.min.js
* Added php code in the folloing files to show text:
/application/views/appointments/book.php
/application/controllers/Appointments.php

For more details theck [git comparison](https://github.com/eellak/easyappointments/compare/master...eellak:easyappointments:gfoss-adjusted#diff-39f98e2c8fe6c21881031e3f11a2a4931857a8a624a69d3895ea2f08dc0e996bL38) .


**To access our working demo contact us at info@eellak.gr.**


## License 

Code Licensed Under [GPL v3.0](https://www.gnu.org/licenses/gpl-3.0.en.html) | Content Under [CC BY 3.0](https://creativecommons.org/licenses/by/3.0/)

---

Website [alextselegidis.com](https://alextselegidis.com) &nbsp;&middot;&nbsp;
GitHub [alextselegidis](https://github.com/alextselegidis) &nbsp;&middot;&nbsp;
Twitter [@alextselegidis](https://twitter.com/AlexTselegidis)

###### More Projects On Github
###### ⇾ [Plainpad &middot; Self Hosted Note Taking App](https://github.com/alextselegidis/plainpad)
###### ⇾ [Questionful &middot; Web Questionnaires Made Easy](https://github.com/alextselegidis/questionful)
###### ⇾ [Integravy &middot; Service Orchestration At Your Fingertips](https://github.com/alextselegidis/integravy)

# P5-Linux Server Configuration
Project 5 of Udacity Full Stack Web Developer nanodegree

IP Address: 52.35.141.29
SSH Port: 2200
Website: http://ec2-52-35-141-29.us-west-2.compute.amazonaws.com/
user: grader

# How to login
 1) Copy the key from the "notes to the reviewer" section.
 2) Create a file in you ~/.ssh directory named "udacity_key.rsa"
 3) Paste the key into that file.
 4) Change the permissions on that file to 600
 5) SSH into the box with the following command
    ssh -i ~/.ssh/udacity_key.rsa grader@52.35.141.29 -p 2200

# Software Installed (using sudo apt-get install)
 1) ntp
 2) apache2
 3) libapache2-mod-wsgi
 4) postgresql
 5) python-pip
 6) python-flask
 7) python-sqlalchemy
 8) python-psycopg2
 9) git

# Python packages (using sudo pip install)
 1) virtualenv
 2) dicttoxml
 3) httplib2
 4) oauth2client

# Configuration changes made
 1) Gave grader sudo permissions
 2) Gave grader ssh capabilities
 3) Removed root from being able to ssh into the machine
 4) Made grader the only user that can ssh
 5) Changed the ssh port to 2200
 6) Updated/upgraded all software on the machine
 7) Enabled a firewall that only allows connections on ports 80, 123, and 2200
 8) Sync'd the machine clock to NTP servers
 9) Created a postgresql db
 10) Updated pg_hba.conf so only the local machine has access to the db 
 11) Disabled the default apache2 website and enabled the item catalog app
 12) Additionally, some code updates were required to get the catalog app up and running
     a. Switched out sqlite to postgresql for the db
     b. Moved the contents of application.py to __init__.py
     c. Used full paths to refer to the client secret files

# Third Party resources
 1) The Udacity class Configuring Linux Web Servers [https://www.udacity.com/course/progress#!/c-ud299-nd]
 2) Links from the Linux Server Configuration: Getting Started doc
     a. Markedly underwhelming and potentially wrong resource list for P5 [https://discussions.udacity.com/t/markedly-underwhelming-and-potentially-wrong-resource-list-for-p5/8587]
         i. Particularly helpful to me from here:
             - Granting sudo privileges to an existing user [http://askubuntu.com/questions/168280/how-do-i-grant-sudo-privileges-to-an-existing-user]
             - Deploy a Flask App on Ubuntu [https://www.digitalocean.com/community/tutorials/how-to-deploy-a-flask-application-on-an-ubuntu-vps]
             - PostgreSQL docs on pg_hba.conf [http://www.postgresql.org/docs/9.1/static/auth-pg-hba-conf.html]
             - Using PostgreSQL with Flask [http://killtheyak.com/use-postgresql-with-django-flask/]
             - Graceful way to change SSH port and UFW [https://discussions.udacity.com/t/graceful-way-to-change-ssh-port-and-ufw/4830]
     b. Project 5 Resources [https://discussions.udacity.com/t/project-5-resources/28343]
         ii. Particularly helpful to me from here:
             - Apache2 web server [https://help.ubuntu.com/lts/serverguide/httpd.html]
             - VirtualHost Directive [http://httpd.apache.org/docs/2.2/en/mod/core.html#virtualhost]
             - PostgreSQL [https://help.ubuntu.com/community/PostgreSQL]
             - Time Sync with NTP [https://help.ubuntu.com/lts/serverguide/NTP.html]
 4) Linux Server Configuration by robertavram [https://github.com/robertavram/Linux-Server-Configuration#apache-flask-application-container]
 5) Diabling root login [http://www.howtogeek.com/howto/linux/security-tip-disable-root-ssh-login-on-linux/]

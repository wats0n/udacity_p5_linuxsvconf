# Project 5 : Linux Server Configuration

Udacity project 5 aims configure Liunx server preferences and setup security functions.
For this project, I initialized a web-server from catalog project and modified for PostgreSQL.

## Quick Start

- IP address: 52.37.226.123
- SSH Port: 2200
- Restaurant Catalog Project Link: 
  * http://52.37.226.123/restaurant/
- Connect Server by following command in Git Bash Shell:
  * `ssh -i udacity_key.rsa grader@52.37.226.123 -p 2200`
- Catalog Project at `/var/www/html/catalog/` directory.

## Installed Software
### apt-get
    * apache2
    * postgresql 
    * python-psycopg2
    * python-sqlalchemy
    * python-pip
### Python
    * werkzeug
    * flask
    * Flask-Login
    * outh2client
    * requests
    * httplib2
    
## Changed Preference
    * Change SSH to port 2200
    * Configure UFW only allow below connection
        1. port 2200
        2. port 80
        3. port 123/tcp
    * Configure default timezont to UTC
    * Change Python simple web server to Apache server with WSGI function
    * Setup grader sudo timeout every 5 minutes
    * Use `sudo crontab -e` to add auto-update at AM 5:00
    * Add Fail2ban to monitor on 2200 port

## Port flask app to Apache WSGI
    1. create catalog.wsgi
        - Add sys.path and os.chdir for local data dependency
    2. Modify database provider form sqlite to postgresql
        - Add user named `catalog` and new `restaurants` database
    3. Modify project.py for login function
        - Add app.secret_key for flash() function
        - Add `login_session` in global variable for `/login` page to store information

## Creator(s)
------
Watson Huang (wats0n)
03/29, 2016

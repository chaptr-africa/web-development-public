## Connecting Django App with MySQL Database

To connect Django project to a MySQL database, you can follow these steps:

1. Install the MySQL client library for Python. You can do this using pip, the Python package manager, with the following command:

<pre>
       pip install mysqlclient
            Or
       pip install --only-binary :all: mysqlclient
</pre>

2. Install the MySQL server and create a database. You can do this using the appropriate package manager for your operating system. For example, on Windows:
 
	- Download the MySQL Community Server installer from the MySQL website: https://dev.mysql.com/downloads/mysql/

    - Choose the appropriate version for your Windows operating system and download the installer.

    - Run the installer and follow the installation wizard.
You can choose the default options for most of the installation settings, but make sure to set a root password for the MySQL server.
    - Open the mySQL Workbench, log in and create database by running this command:
<pre>
        CREATE DATABASE mydatabase;
</pre>

## On Ubuntu, follow the steps here
 https://www.mysqltutorial.org/install-mysql-ubuntu/


3. In your Django project's settings.py file, add the following database     configuration:
<pre>
# settings.py


DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'mydatabase',
        'USER': 'your_mysql_username',
        'PASSWORD': 'your_mysql_password',
        'HOST': 'localhost',
        'PORT': '3306',
    }
}

</pre>

- Replace your_mysql_username and your_mysql_password with your MySQL username and password, respectively. 
- You may also need to adjust the HOST and PORT settings if your MySQL server is running on a different host or port.

4. Run the Django migrations to create the necessary database tables:

<pre>
      python manage.py migrate
</pre>

This will create the tables defined by Django's built-in apps (such as auth and admin) in your MySQL database.

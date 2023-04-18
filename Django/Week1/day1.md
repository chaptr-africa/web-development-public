## Introduction

<!-- <a href="https://youtu.be/SIyxjRJ8VNY">Watch Introduction Tutorial</a> -->

By the end of the Django module, you will be able to: 

<ol> 
<li>Create a Django application and have it running on the Django development server.</li>
<li>Create view functions in a Django application.
</li>
<li>Configure URLs to different views or pages in a Django application.</li>
<li>Create templates and use template syntax in a Django application.
</li>
<li>Create a database and connect a Django application to the database.
</li>
<li>Create tests that check for the behavior of our code in our applications.
</li>
<li>Activate and use the Django admin to work with data in the application's models.
</li>
<li>Create a feature for uploading images in a Django web app.
</li>
<li>Create web forms for collecting and storing user data in the database.</li>
<li>Authenticate users into and out of a Django app through signup, login, and logout features.</li>
<li>Create an API that has data from our Django application's models.
</li>
<li>Configure a Django app for deployment to render.
</li>
</ol>

## Model-View-Template (MVT) Design 

<!-- <a href="https://youtu.be/GGkFg52Ot5o">Watch MVTj Tutorial</a> -->

Django follows the Model-View-Controller (MVC) architectural pattern, but with some slight variations since In Django, the MVC pattern is implemented as Model-View-Template (MVT) as you can see below:

<ul>
<li><b>Model:</b> The Model layer in Django represents the data of the application and provides an interface to work with the database. Models are typically defined as Python classes that inherit from the django.db.models.Model class.
</li>
<li><b>View: </b>The View layer in Django receives requests from the client, retrieves data from the Model layer, and returns a response to the client. Views are typically defined as Python functions or classes that receive an HTTP request and return an HTTP response.
</li>
<li><b>Template</b> The Template layer in Django is responsible for rendering the HTML pages that are sent to the client. Templates can contain placeholders for dynamic content that are filled in by the View layer. Templates are typically written in HTML with embedded Python code using Django's template language.
</li>
</ul>



## Setting up the Development Environment

### Linux and Mac:

<ol> 
<li><b>Install Python:</b> The first step is to install Python on your machine. Most Mac and Linux systems come with Python pre-installed, but you can check by running,  <b>python --version</b> in your terminal. If Python is not installed, follow this <a href="https://www.python.org/downloads/">process</a> to install.  
</li>
<li><b>Install pip: </b>Once you have Python installed, you need to install pip, which is a package manager for Python. To install pip, type <b>sudo easy_install pip</b> in your terminal.
</li>
<li><b>Install virtualenv:</b> Virtualenv is a tool that creates isolated Python environments for your projects. It's recommended to use virtualenv to avoid conflicts between different projects' dependencies. To install virtualenv, type <b>sudo pip install virtualenv</b> in your terminal.
</li>
<li><b>Create a virtual environment:</b> To create a virtual environment, navigate to the directory where you want to create it and type <b>virtualenv myenv</b>. This will create a new directory called myenv that contains a clean Python installation with its own set of packages.
</li>
<li><b>Activate the virtual environment:</b> To activate the virtual environment, type <b>source myenv/bin/activate</b>. You should see the name of the virtual environment in your terminal prompt
</li>
<li><b>Install Django:</b> With the virtual environment activated, you can now install Django by typing <b>pip install Django</b>
</li>
</ol>

### Alternatively:
 Install and activate virtual environment directly together with pip

<pre>
$ python3 -m venv virtual 
$ source virtual/bin/activate  

</pre>

### Windows:

<!-- <a href="https://youtu.be/VuETrwKYLTM">Watch Tutorial</a> -->
<ol> 
<li><b>Install Python:</b> The first step is to download and install Python from the official <a href="https://www.python.org/downloads/">Website</a>.
</li>
<li><b>Install pip: </b>Once you have Python installed, you need to install pip. To do this, download get-pip.py from <a href="https://bootstrap.pypa.io/get-pip.py">https://bootstrap.pypa.io/get-pip.py</a> and run it by double-clicking on the file.

</li>
<li><b>Install virtualenv:</b> To install virtualenv, type <b>pip install virtualenv</b>  in your command prompt.
</li>
<li><b>Create a virtual environment:</b> To create a virtual environment, navigate to the directory where you want to create it and type <b>virtualenv myenv</b>. This will create a new directory called myenv that contains a clean Python installation with its own set of packages.
</li>
<li><b>Activate the virtual environment:</b> To activate the virtual environment, type <b>myenv\Scripts\activate</b>. You should see the name of the virtual environment in your terminal prompt
</li>
<li><b>Install Django:</b> With the virtual environment activated, you can now install Django by typing <b>pip install Django</b>
</li>
</ol>



### Create the First Django App

<ol> 
<li>Open your Terminal/Command Prompt/PowerShell/Git Bash and navigate to the directory where you want to create your Django project.
</li>
<li>Create and activate your virtual environment.
</li>
<li>Create a new Django project using the <b>django-admin startproject</b> command. For example, if you want to create a project called "myproject", type:  
<pre>(virtual) $ django-admin startproject myproject . </pre>
The folder structure looks like this;
<pre>
manage.py
mypoject/
    __init__.py
    settings.py
    urls.py
    wsgi.py
</pre>

</li>
<li>Create a new Django app using the <b>python manage.py startapp</b> command. For example, if you want to create an app called "myapp", type:
<pre>(virtual)$ python manage.py startapp myapp</pre>
The myapp folder structure looks like this;
<pre>myapp/
    __init__.py
    admin.py
    apps.py
    migrations/
        __init__.py
    models.py
    tests.py
    views.py
</pre>
</li>
<li>Open the settings.py file in your project directory and add your app to the <b>INSTALLED_APPS</b> list. For example:
<pre>
# myproject/settings.py
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'myapp', # Add your app here
]

</pre>
</li>
<li>Create a view function in your app's views.py file. For example:
<pre>
# myapp/views.py


from django.http import HttpResponse


def helloWorld(request):
    return HttpResponse("Hello, world!")
</pre>
</li>
<li>Create a URL pattern for your view function in your app's urls.py file. For example:
<pre>
# myapp/urls.py
from django.urls import path
from . import views
urlpatterns = [
    path('helloWorld/', views.helloWorld, name='hello'),
]
</pre>
</li>
<li>Include your app's URL configuration in your project's urls.py file. For example:
<pre>
# myproject/urls.py
from django.contrib import admin
from django.urls import include, path
urlpatterns = [
    path('admin/', admin.site.urls),
 path(' ', include('myapp.urls')),
]
</pre>
</li>
<li>Run the development server using the python manage.py runserver command and visit <pre> http://localhost:8000/myapp/helloWorld/ </pre> in your web browser to see your app in action. For example:
<pre>(virtual) $ python manage.py runserver </pre>

</li>

</ol>

## Challenge Task

In this challenge, you will create a new Django project and app, and display a custom message on the homepage saying "Welcome to my Django app!".

## Challenge Submission
Submit your code as a GitHub repository, and include a README file with instructions on how to set up and run the app. Don't forget to include the URL mappings, view functions, and template files.




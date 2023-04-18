## Adding Bootstrap

Bootstrap is a popular front-end framework that provides pre-designed HTML and CSS components for creating responsive and mobile-friendly web pages. Django makes it easy to add Bootstrap to your project by using third-party packages such as <b>django-bootstrap4</b>.

Here are the steps to add Bootstrap to your Django project using django-bootstrap4:

1. Install django-bootstrap4 using pip:
<pre>
    $ pip install django-bootstrap4
</pre>
2. Add 'bootstrap4' to the INSTALLED_APPS list in your project's settings.py file:
<pre>
       # settings.py


       INSTALLED_APPS = [
       # ...
       'bootstrap4', 
       # ...
     ]
</pre>
3.  In your base template, load the bootstrap4 tags and use them to include the   necessary CSS and JavaScript files:
<pre>
&lt;!-- base.html -->

{% load bootstrap4 %}

&lt;!DOCTYPE html>
&lt;html>
&lt;head>
    &lt;title>{% block title %}My Site{% endblock %}</title>
    &lt;!-- common CSS files -->
    {% bootstrap_css %}
&lt;/head>
&lt;body>
    {% block content %}
    &lt;!-- content specific to child templates -->
    {% endblock %}
    &lt;!-- common JavaScript files -->
    {% bootstrap_javascript %}
&lt;/body>
&lt;/html>
</pre>

4. Use Bootstrap components and styles in your child templates by using the appropriate bootstrap4 tags:
<pre>
&lt;!-- index.html -->


{% extends "base.html" %}


{% block title %}My Child Page{% endblock %}


{% block content %}
&lt;!-- content specific to child template -->
&lt;div class="container">
  &lt;div class="row">
    &lt;div class="col-sm-6">
      &lt;h1>Hello, World!</h1>
    &lt;/div>
    &lt;div class="col-sm-6">
      &lt;button type="button" class="btn btn-primary">Click Me</button>
    &lt;/div>
  &lt;/div>
&lt;/div>
{% endblock %}
</pre>

## Connecting CSS

  To connect CSS to your Django project, you can follow these steps:
1. Create a static directory in your Django application. This directory will store your static files, such as CSS, JavaScript, and images.
1. Inside the static directory, create a subdirectory for your CSS files. For example, you could create a css directory.
3. In the css directory, create a CSS file. For example, you could create a styles.css file.
4. In your Django template, load static tags and add a link to your CSS file in the &lt;head> section. You can use the {% static %} template tag to generate the URL for your CSS file. Here's an example:
<pre>
 &lt;!-- base.html -->
{% load bootstrap4 %}
{% load static %}


&lt;!DOCTYPE html>
&lt;html>
&lt;head>
    &lt;title>{% block title %}My Site{% endblock %}</title>
    &lt;!-- common CSS files →
  &lt;link rel="stylesheet" type="text/css" href="{% static 'css/styles.css' %}">
    {% bootstrap_css %}
&lt;/head>
&lt;body>
    {% block content %}
    &lt;!-- content specific to child templates -->
    {% endblock %}
    &lt;!-- common JavaScript files -->
    {% bootstrap_javascript %}
&lt;/body>
&lt;/html>
</pre>

5. Write your CSS code in the styles.css file. For example, you could add the following code to change the background color of the body element:
<pre>
/* styles.css */

body {
    background-color: #f0f0f0;
}
</pre>
6. Finally, make sure that your Django project is configured to serve static files during development. In your project's settings.py file, add the following:
<pre>
# settings.py

# ...

STATIC_URL = '/static/'
STATICFILES_DIRS = [BASE_DIR / "static"]

# ...
</pre>
This tells Django to serve static files from the static directory in your application.
With these steps, you should be able to connect CSS to your Django project and customize the styles of your pages.


## Challenge Task

In this challenge,  you will add Bootstrap and custom CSS styles to a Django app you developed on day 3 to create a responsive and visually appealing web page.

## Challenge Submission
Submit your code as a GitHub repository, and include a README file with instructions on how to set up and run the app. Don't forget to include the URL mappings, view functions, and template files.
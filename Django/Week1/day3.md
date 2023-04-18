## Template Inheritance

Template inheritance is a powerful feature in Django that allows you to create a base template that defines the overall structure and layout of your web pages, and then extend that base template in other templates to add specific content.
Here's how template inheritance works:

<ol> 
<li>Create a base template that contains the common elements of your web pages (e.g., header, navigation menu, footer). This template should define blocks where content can be inserted. i.e  base.html inside your templates folder.
<pre>
&lt;!--base.html -->
&lt;!DOCTYPE html>
&lt;html>
&lt;head>
    &lt;title>{% block title %}My Site{% endblock %}&lt;/title>
    &lt;!-- common CSS and JavaScript files -->
&lt;/head>
&lt;body>
    {% block content %}
    &lt;!-- content specific to child templates -->
    {% endblock %}
    &lt;!-- common footer -->
&lt;/body>
&lt;/html>
&lt;/pre>
</li>
<li>
Inherit from the base template in child templates by using the extends template tag. Child templates can override or add to the blocks defined in the base template.
<pre>
&lt!-- index.html -->


{% extends "base.html" %}


{% block title %}My Child Page{% endblock %}


{% block content %}
&lt;!-- content specific to child template -->
&lt;h1>Hello, World!</h1>
{% endblock %}
</pre>
</li>

</ol>

## Challenge Task

In this challenge, you will create a new Django app with multiple templates, and implement template inheritance to display a custom message using the base template.Also add a Navbar that is displayed on all the pages 

## Challenge Submission
Submit your code as a GitHub repository, and include a README file with instructions on how to set up and run the app. Don't forget to include the URL mappings, view functions, and template files.
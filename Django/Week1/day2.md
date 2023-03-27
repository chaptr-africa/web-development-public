## Create Templates
In Django, templates are used to separate the presentation logic from the application logic. They allow you to define the layout and structure of your web pages in a separate file, which can be reused and modified easily.

To add templates to your Django project, you need to follow these steps:

<ol> 
<li>Create a templates directory in your Django app directory. This is the default directory where Django looks for templates.
</li>
<li>Create a new HTML file in the templates directory. This file will contain the HTML code for your web page.
</li>
<li>In your view function, create a render function that takes the request object and the path to your HTML file. The render function returns an <span style='color: green'>HttpResponse</span> object that contains the rendered HTML.

</li>
<li>In your <span style='color: green'>urls.py</span> file, add a new path that maps to your view function.
</li>
</ol>

Here's an example of how to add a template to your Django app:

<ol> 
<li>Create a templates directory in your app directory:
<pre> 
    myapp/
        templates/
</pre>
</li>
<li>.Create a new HTML file in the templates directory:
<pre>
              myapp/
                templates/
                   index.html
</pre>
</li>
<li>In your view function, import the render function and use it to render the index.html template:
<pre>
from django.shortcuts import render
def index(request):
    return render(request, 'index.html')
</pre>

</li>
<li>.  In your urls.py file, add a new path that maps to your view function:
<pre>
from django.urls import path
from . import views
    urlpatterns = [
    path('', views.index, name='index'),
    ]
</pre>
</li>
</ol>

Now, when a user visits the root URL of your app, Django will call the index view function, which will render the index.html template and return it as a response. The user will see the HTML rendered in their browser.
You can also pass variables from your view function to your template, which allows you to dynamically generate content based on user input or database queries. To do this, you can pass a dictionary of variables to the render function:

<pre>

   def index(request):
     context = {'message': 'Hello, world!'}
     return render(request, 'index.html', context)

</pre>

In your index.html template, you can access the message variable using Django's template syntax:
<pre>
&lt;h1>{{ message }}&lt;/h1>
</pre>

Run the development server using the python manage.py runserver command and visit 
<pre>
 http://localhost:8000/ 
</pre>
in your web browser to see your app in action. For example:
<pre>
(virtual) $ python manage.py runserver
</pre>
 You should be able to see  <b>Hello, world! </b> On your browser

## Displaying model Data

### Create Views

- We now create a view in the views.py file that retrieves all the Blog objects from the database and renders them in a template:

<pre>
from django.shortcuts import render
from .models import Blog

def blog_list(request):
    blogs = Blog.objects.all()
    context = {'blogs': blogs}
    return render(request, 'blog_list.html', context)

</pre>

- the blog_list function is a view that takes a request object as a parameter and returns an HTTP response. The view retrieves all the Blog objects from the database using the Blog.objects.all() method, and stores them in a blogs variable.

- The view then creates a context dictionary with a key 'blogs' and the blogs variable as the value. This context dictionary will be used to pass data to the template.

- Finally, the view renders a template named 'blog_list.html' using the render function. The render function takes three arguments:

  1. The request object
  2. The name of the template to render (in this case, 'blog_list.html')
  3. The context dictionary to pass data to the template

### Create Template

You can now create the blog_list.html template in your app's templates directory as seen below:

<pre>
{% extends 'base.html' %}

{% block content %}
    &lt;h1>Blog Posts&lt;/h1>
    {% for blog in blogs %}
        &lt;h2>{{ blog.title }}&lt;/h2>
        &lt;p>By {{ blog.author.username }} on {{ blog.published_date }}&lt;/p>
        &lt;p>{{ blog.text }}&lt;/p>
    {% endfor %}
{% endblock %}

</pre>

- In this, the template extends a base template named 'base.html' and defines a block named 'content'. Inside the 'content' block, the template uses a for loop to iterate over the blogs variable that was passed from the view.

- For each Blog object, the template displays the title, author's username, date posted, and content using the {{ }} template syntax.

### Create URLs

- Once you've created the view and the template, you can create a URL pattern to map a URL to the view. For example, you could add the following line to your app's urls.py file:
<pre>
from django.urls import path
from . import views

urlpatterns = [
    path('blog/', views.blog_list, name='blog_list'),
]

</pre>
- This creates a URL pattern that maps the URL http://127.0.0.1:8000/blog/ to the blog_list view. When a user visits this URL, Django will call the blog_list view, retrieve all the Blog objects from the database, and render them in the blog_list.html template.
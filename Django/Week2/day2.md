## Creating Models


To create models in Django, you will need to define a Python class that inherits from django.db.models.Model. Each attribute of the class represents a field in the database table that the model maps to. Django supports a variety of fields for different types of data, such as text, numbers, dates, and more.

Here's an example of a simple Django model for a blog in our simple Blog website:

<pre>
from django.db import models
from django.utils import timezone
from django.contrib.auth.models import User

class Blog(models.Model):
    title = models.CharField(max_length=255)
    author = models.ForeignKey('auth.User', on_delete=models.CASCADE)
    text = models.TextField()
    created_date = models.DateTimeField(auto_now_add=True)
    published_date = models.DateTimeField(blank=True, null=True)
    

    def __str__(self):
        return self.title
</pre>


- The Blog model has four fields:

- title: a CharField with a maximum length of 200 characters that stores the title of the blog post.
- content: a TextField that stores the content of the blog post.
- date_posted: a DateTimeField that stores the date and time when the blog post was created. The default argument sets the default value to the current time zone.
- author: a ForeignKey that stores a reference to the User model, which represents the author of the blog post. The on_delete argument specifies what should happen when the User object is deleted. In this case, the CASCADE option deletes all the Blog objects associated with the deleted User.
- The __str__ method returns the title of the blog post as the string representation of the object.

Once you have defined your model, you will need to create a database table to store the data. To do this, you can use Django's migrations system, which allows you to version-control your database schema and apply changes over time. Here are the basic steps:
1. Run the following command to create an initial migration for your app:
<pre>
  $  python manage.py makemigrations myapp
</pre>

- This will generate a Python file in the myapp/migrations directory that describes the changes to your models.

2. Run the following command to apply the migration and create the database table:
<pre>
  $ python manage.py migrate
</pre>
This will execute the migrations that have not been applied yet.

## Django Admin Site

To add the Tag and Blog model to the admin site, you can register them with the admin site in the admin.py file as seen below:

<pre>

from django.contrib import admin
from .models import Blog

admin.site.register(Blog)

</pre>

- You now need to need a superuser account for the django admin site by running this command: 

<pre>
   $ python manage.py createsuperuser

</pre>
- You'll be prompted to enter a username, email, and password for the superuser account. Follow the prompts and enter the required information.

- Once you've entered the information, press Enter to create the superuser account.
- Rerun your server.
- You can now use the superuser account to log in to the admin site at http://127.0.0.1:8000/admin and access all the features that require administrative privileges.

## Add Sample Posts

- To add two sample blog posts to the Django admin site, you can follow these steps:

  1. Navigate to the Django admin site in your web browser (http://127.0.0.1:8000/admin by default).

  2. Log in with your superuser account credentials.

  3. Click on the "Blog" link to navigate to the blog post list view.

  4. Click on the "Add Blog" button to create a new blog post.

  5. Fill in the form with the following information:

     - Title: "My First Blog Post"
     - Author: [select your user account from the drop-down list]
     - text: "This is my first blog post on this website!"


  6. Click on the "Save" button to save the new blog post.

  7. Repeat steps 4-6 to add another sample blog post:

     Fill in the form with the following information:

      - Title: "My Second Blog Post"
      - Author: [select your user account from the drop-down list]
      - Text: "This is my second blog post, and it's about Django."


   Click on the "Save" button to save the new blog post.

   Navigate back to the blog post list view to see your two new blog posts listed.

   You should now have two sample blog posts in your Django application that you can use to test your views and templates.
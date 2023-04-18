## Django Subscription & News Letters

- Django newsletters are a set of tools that allow developers to easily build and manage email newsletters and campaigns within a Django web application. It provides a flexible framework for creating and sending newsletters to subscribers, tracking open and click-through rates, and managing mailing lists. With Django newsletters, developers can create custom email templates, schedule newsletter delivery, and personalize email content based on subscriber preferences.

- Now let us add newsletter email subscription to your Django blog site app:

  1. Create a Subscriber model to store email addresses of subscribers:

<pre>
# blog/models.py

from django.db import models

class Subscriber(models.Model):
    email = models.EmailField(unique=True)
    created_at = models.DateTimeField(auto_now_add=True)

    def __str__(self):
        return self.email
</pre>

- In this model, we have defined an `EmailField` to store the email address of the subscriber and a `DateTimeField` to store the date and time the subscriber was added to the database. The `unique=True` parameter ensures that each email address is only added once to the database.

  2. Create a view function to handle email subscription:

<pre>
# blog/views.py

from django.shortcuts import render, redirect
from django.contrib import messages
from .models import Subscriber

def subscribe(request):
    if request.method == 'POST':
        email = request.POST['email']
        if Subscriber.objects.filter(email=email).exists():
            messages.error(request, 'You are already subscribed.')
        else:
            subscriber = Subscriber(email=email)
            subscriber.save()
            messages.success(request, 'Thank you for subscribing!')
            return redirect('subscribe')
    return render(request, 'subscribe.html')

</pre>

   - In this code, we first check if the email address already exists in the database using the `filter()` method. If it does, we display an error message. If it doesn't, we create a new `Subscriber` object and save it to the database using the `save()` method. Finally, we display a success message and redirect the user back to the subscribe page.

       3. Create a HTML form to display the subscription form:
<pre> 
&lt;!-- templates/subscribe.html -->

{% extends 'base.html' %}

{% block content %}
  &lt;h2>Subscribe to our newsletter&lt;/h2>
  {% if messages %}
    {% for message in messages %}
      &lt;div class="alert alert-{{ message.tags }}">
        {{ message }}
      &lt;/div>
    {% endfor %}
  {% endif %}
  &lt;form method="post" action="{% url 'subscribe' %}">
    {% csrf_token %}
    &lt;div class="form-group">
      &lt;label for="email">Email address&lt;/label>
      &lt;input type="email" class="form-control" id="email" name="email" required>
    &lt;/div>
    &lt;button type="submit" class="btn btn-primary">Subscribe&lt;/button>
  &lt;/form>
{% endblock %}


</pre>  

   - In this code, we have defined a form with an email input field and a submit button. We have also included a check for messages and displayed them if they exist.

      4. Add a URL pattern for the subscribe view:

<pre>
# blog/urls.py

from django.urls import path
from . import views

urlpatterns = [
    # other URL patterns
    path('subscribe/', views.subscribe, name='subscribe'),
]

</pre>

   - In this code, we have defined a URL pattern for the subscribe view.
   - You can now run yor server the navigate to `http://127.0.0.1:8000/subscribe/` and see the email subscription form. 

## Challenge Task

You have been tasked with implementing an email subscription feature in a web application. The goal is to allow users to subscribe to receive email updates about the web application's latest news, updates, and blog posts.

Here are the steps to complete the challenge:

- Create a new model to store email subscriptions. The model should include the following fields:

1. Email address (string)
2. Subscription date (date/time)
3. Create a form on the web application's homepage that allows users to enter their email address and subscribe to the email list.

- Implement server-side validation to ensure that the email address is valid and not already subscribed.

- Add a confirmation message to the form to let users know that their subscription was successful.

- Create a backend script to send the email updates to all subscribers. The script should run at regular intervals (e.g. daily, weekly) and should send the latest news, updates, and blog posts to all subscribers.

- Add an "Unsubscribe" link in the emails that allows users to easily unsubscribe from the email list.

## Challenge Submission
Submit your code as a GitHub repository, and include a README file with instructions on how to set up and run the app. Don't forget to include the Model, URL mappings, view functions, and template files.
---
layout: page
weight: 0
title: Django
seo:
  title: Send Email with Django & SendGrid
  description: View instructions on how to easily send email with Django using SendGrid, by setting up setting up Django's built in mail library.
navigation:
  show: true
---

There is more detailed information about [sending email with Django](https://docs.djangoproject.com/en/dev/topics/email/) on the Django project website.

First start by adding the following to **settings.py:** 

{% codeblock lang:python %}
EMAIL_HOST = 'smtp.sendgrid.net'
EMAIL_HOST_USER = 'sendgrid_username'
EMAIL_HOST_PASSWORD = 'sendgrid_password'
EMAIL_PORT = 587
EMAIL_USE_TLS = True
{% endcodeblock %}

 Then to send email you can do the following: 

{% codeblock lang:python %}

from django.core.mail import send_mail
send_mail('Subject here', 'Here is the message.', 'from@example.com', ['to@example.com'], fail_silently=False)
{% endcodeblock %}

 
{% info %}
You may also send emails with Django by using the [sendgrid-django](https://github.com/elbuo8/sendgrid-django) library, which utilizes the [Web API]({{%20root_url%20}}/API_Reference/Web_API/index.html) instead of SMTP as the transport mechanism. 
{% endinfo %}

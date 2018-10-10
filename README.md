# Django-Celery-Example
This is a simple example about integrating Celery in Django website, it uses celery to run a long task and shows a progress bar about the progress of the task.

![image](https://raw.githubusercontent.com/sunshineatnoon/Django-Celery-Example/master/images/2.png)
![image](https://raw.githubusercontent.com/sunshineatnoon/Django-Celery-Example/master/images/3.png)
![image](https://raw.githubusercontent.com/sunshineatnoon/Django-Celery-Example/master/images/1.png)


# Dependencies

* Celery 4.2.1
* Django 1.9
* RabbitMQ 3.5.6 or Redis 2.4.5

# How to run:
You are advised to create a special environnement to test it !
```
  git clone https://github.com/sunshineatnoon/Django-Celery-Example.git
  cd Django-Celery-Example
  pip install -r requirements.txt
  /usr/local/sbin/rabbitmq-server
  celery -A celery_try worker -l info
  python manage.py makemigrations
  python manage.py migrate
  python manage.py runserver
```
You could change rabbitmq-server by redis-server

Then visit [http://127.0.0.1:8000/index/](http://127.0.0.1:8000/index/).

# Technical Details: 

See my [blog post](https://sunshineafternoonweb.wordpress.com/2017/01/30/first-blog-post/)
or [annother resource](https://buildwithdjango.com/blog/post/celery-progress-bars/).

# Known Issue:

Works well on firefox and chrome, but doesn't work on safari.
Works on [windows with eventlet](https://stackoverflow.com/a/47331438/4989371) :
```
pip install eventlet
celery -A celery_try worker -l info -P eventlet
``` 
 


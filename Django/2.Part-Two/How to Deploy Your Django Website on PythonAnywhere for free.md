## 3. How to Deploy Your Django Website on PythonAnywhere for free?

1. Go to: [pythonanywhere.com](https://www.pythonanywhere.com/)

2. Then click on: **Pricing & signup** 

3. Then click on: **Create a Beginner account**
```python 
   * (your-username.pythonanywhere.com)

	Username: shoriot

	Email:  sdshoriot@gmail.com

	Password: ********

        Password (again): ********
```
4. Now: **Log in**
```python 
Username: shoriot

Password: ********
```
5. Now click on: **Web** 

6. Then click on:   **Add a new web app**

7. Then click on: **Next**

8. Then select: **» Manual configuration**

9. Then Select a Python version as you wish like: (**» Python 3.6**)

10. Then click on:  **Next**

Now see your domain name: Configuration for [shoriot.pythonanywhere.com](http://shoriot.pythonanywhere.com/)

11. Now click on: **Consoles**

12. Then click on: **Bash**
```python
13. (Write in home of Bash console): >>> git clone

>>> ls
>>> cd shoriot

>>> virtualenv -p python3 venv
>>> source venv/bin/activate

>>> pip install django
```
14. Now click on: **Web**

15. **Source code**: /home/shoriot/shoriot

16. **Virtualenv**: /home/shoriot/shoriot/venv

17. **URL**: /static/    

18. **Directory**: /home/shoriot/shoriot/static
```python
>>> python manage.py collectstatic
```
19. Now click on: **WSGI configuration file**:  /var/www/shoriot_pythonanywhere_com_wsgi.py

```python
* Comment all code without this part.
# +++++++++++ DJANGO +++++++++++
# To use your own django app use code like this:
import os
import sys
#
## assuming your django settings file is at '/home/shoriot/mysite/mysite/settings.py'
## and your manage.py is is at '/home/shoriot/mysite/manage.py'
path = '/home/shoriot/shoriot'
if path not in sys.path:
    sys.path.append(path)
#
os.environ['DJANGO_SETTINGS_MODULE'] = 'banglaidj.settings'
#
## then:
from django.core.wsgi import get_wsgi_application
application = get_wsgi_application()
```
20. Now click on: **Files**

```python
& go to:   /home/shoriot/shoriot/banglaidj/settings.py

ALLOWED_HOSTS = ['*']
```

21. Now click on: **Web**

*  then Reload your web app, click on: **Reload shoriot.pythonanywhere.com**

*  To see your website live, click on: Configuration for [shoriot.pythonanywhere.com](http://shoriot.pythonanywhere.com/)



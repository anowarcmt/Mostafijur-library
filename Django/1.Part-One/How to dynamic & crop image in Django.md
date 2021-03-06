# 2. How to dynamic & crop image in Django?

### How to dynamic image in Django?

```python
1. $ pip install Pillow


2. project/settings.py

...
STATIC_ROOT = os.path.join(os.path.dirname(BASE_DIR), 'static_root')

MEDIA_URL = "/media/"
MEDIA_ROOT = os.path.join(os.path.dirname(BASE_DIR), 'media_root')


3. project/urls.py

...
from django.conf import settings
from django.conf.urls.static import static

...
if settings.DEBUG:
    urlpatterns += static(settings.STATIC_URL, document_root=settings.STATIC_ROOT)
    urlpatterns += static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)


4. app/models.py

...
img = models.ImageField(upload_to='author_images', null=True, blank=True)


5. app/author.html

...
<img src="/media/{{ author.img }}" alt="">
```

### How to crop image in Django?

#### To crop image Just add this code with "How to dynamic image in Django?" part.
```python
1. $ pip install sorl-thumbnail


2. project/settings.py

INSTALLED_APPS = [
	...
    'sorl.thumbnail',
]


3. app/models.py

...
from sorl.thumbnail import ImageField


4. app/author.html

{% extends 'base.html' %}
{% load thumbnail %}
{% block content %}

...
{% thumbnail author.img "150x150" crop="center" as im %}
    <img src="{{ im.url }}" width="{{ im.width }}" height="{{ im.height }}">
{% endthumbnail %}
```



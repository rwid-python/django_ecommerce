# django_ecommerce
Install & Configure Django :
1. pip install django --> for install django
2. django-admin startproject ecommerce --> for create project
3. cd ecommerce/ --> move to folder project
4. python manage.py startapp store --> create self project
5. python manage.py runserver --> run web django
6. url access django : http://127.0.0.1:8000
---------
---------
Create Template :
1. Create folder : template on store
2. Create html file : store.html; main.html; checkout.html; cart.html
3. Declare file html on views.py
4. Create urls.py to config url views
5. Import urls.py from store to urls.py in default django
   path('', include('store.urls'))
---------
---------
Static File : for css & images
1. Create folder : css & images on static
2. Create default page : main.html (as a template) and default css use : main.css   
3. Initial static folder on settings.py : STATICSFILES_DIRS
4. Add {% extends 'store/main.html' %}; {% load static %}; {% block content %}; {% endblock content %} for every page
5. Add div with class = "container" for fill content in every page use  {% block content %} ..... {% endblock content %}
6. Create page main.html use bootstrap template : navbar
7. Modify main.html as a template. <br>
   7.1. Add button, link on django use : {% url page %} *url define on urls.py on application folder <br>
   7.2. Custom css file / css.main
8. Create default page : main.html --> store.html
9. Create others page as : cart, checkout
---------
---------
Database / Models on django :
1. Create database use model
    <br> 1.1. Create database from file model.py
    <br> 1.2. Create table use : class (as Customer, Product, Order, OrderItem, ShippingAddress)
    <br> 1.3. Create field at every table, format : name field = model.datatype(attribute)
    <br> --> data type : ForeignKey, BooleanField, DateTimeField, CharField, IntegerField, DecimalField, FloatField, etc.
    <br> --> attribute : null=True, max_length=20, blank=True, etc) 
    <br> 1.4. Migration Syntax on terminal :
    <br> --> a. python migrate.py makemigrations
    <br> --> b. python migrate.py migrate
2. Show data / model to view
    <br> 2.1. Import : 
    <br> --> from django.contrib import admin
    <br> --> from .models import *
    <br> 2.2. Register table : admin.site.register(table name)
    <br> 2.3. Create default superuser from terminal : python manage.py createsuperuser 
    <br> 2.4. Input from web django administrator : localhost:8000/admin
    <br> 2.5. Syntax initial on view.py : context = { 'products': products }
    <br> 2.6. Show on html use loop & show detail of product 
    <br> --> {% for product in products %} ..... {% endfor %}
    <br> --> {{product.name_field}} ##declare show field
    <br> 2.7. Syntax from update model used 10.4 (makemigration & migrate)
    <br> 2.8. Show image from django : install pillow
    <br> --> Create Media Url at settings.py : MEDIA_URL= '/images/' & MEDIA_ROOT = os.path.join(BASE_DIR, 'static/images'')
    <br> --> Setting url at urls.py : from django.urls import path, include & from django.conf.urls.static import static & from django.conf import setting
    <br> --> Initial url patterns at urls.py : urlpatterns = static(setting.MEDIA_URL, document_root=setting.MEDIA_ROOT)
---------
---------
Transaction process
<br>
---------
---------

Flow process access page :
- localhost --> url default django --> store.url --> requested page --> page


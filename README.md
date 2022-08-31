# Django-Tutorials
learn to use django

'''
this is how django program runs
--> pip install django (installs django)
--> python manage.py (returns all the methods available for development in python.)

2.to create new project use
--> python manage.py startproject [projectname] 
 (necessary django files are created in the [projectname]folder)

3. to create new application use
--> python manage.py startapp [projectname] 
 (necessary django files are created in the [projectname]folder)

4. Url dispatcher
--> here we redirect url accounding to the request from the user. 
    if user is looking for about page we redirect it to about page
    to do this
    1]create app lets say home
    2]create a new python file named urls.py in Home application
    3] now in the urls.py of the project, add these lines

        from django.contrib import admin
        from django.urls import path,include

        urlpatterns = [
            path('admin', admin.site.urls),
            path('', include('Home.urls')),
        ] # this will re direct http://127.0.0.1:8000/ to admin or '' that is Home.urls
    4] at home.urls
        # from django.contrib import admin
        from django.urls import path
        from Home import views
        urlpatterns = [
            path('', views.home,name='Home'),
            path('about', views.about,name='about'),
        ]if it is empty it will redirect to views.home orelse to aout page
    5] views of an application
        from django.shortcuts import render,HttpResponse
        # Create your views here.
        def home(request):
            return HttpResponse('This is home')
    
        def about(request):
           return HttpResponse('This is about')
5. Static files
    this is a static file. anyone on the web can directly access it.
    that is the contents of the file are readyly available to anyone on the internet
    static file can be a image text video etc.
    1]to create one first create folder names static and create a new file in it
    2]  in the settings add the following lines
        STATICFILES_DIRS=[
        os.path.join(BASE_DIR,"static")
    ] # 

6. use templates to make sites attractive


--> python manage.py runserver(starts the project at http://127.0.0.1:8000/)

django is a we framework written in python. 
it has big collections of modules which is used to cretae own projects

 

'''


alternative to python manage.py we can use django-admin.
![image](https://user-images.githubusercontent.com/100014146/187595047-cbcf47f2-6391-445b-969c-ccc06ac94f7a.png)




a webpage is made using html cs and javascript (front end) but what to show to the user, account atuthentication,etc is done by backend system(django,php asp.net)
eg-  when user request facebook.com for ogin page, at backend of facebook, it sees the request and decided whether to send page or not(here it send as its just home page) now when user tries to login facebook backend sYstem checks for the credential and and decided whether to show the account or block it.


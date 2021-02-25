## Creating lab_exam project

- Installing django
	> pip install django
- Creating our project 
	> django-admin startproject LabExam
-  Running Migrations
	> python manage.py migrate 
- Creating superuser
	> python manage.py createsuperuser
	-  A username, an email address, and a password for your user.
	-   An email
	-   A password (containing at least 8 characters)
- Creating lab_exam app
	> python manage.py startapp lab_exam

## Creating lab_exam model
- Inside lab_exam/models.py
	
	from django.db import models

  

## Creating LabExam Model

### Inside lab_exam/models.py

class  LabExam(models.Model):

	exam_date = models.DateField()

	exam_name = models.CharField(max_length=255)

	exam_description = models.TextField()

	total_marks = models.FloatField(null=True, blank=True)

	pass_marks = models.FloatField(null=True, blank=True)

	exam_status = models.BooleanField()

  
	def  __str__(self):

		return  self.exam_name

## Migration
- Creating migration
	> python manage.py makemigrations lab_exam

## Migrating to database
- Migrating to sqlite
	> python manage.py migrate


## Registering app
- Inside bhola_exam/settings.py
	> INSTALLED_APPS = [

				........

				'lab_exam'

				]
				
## Registering site in admin
- Inside lab_exam/admin.py
```
from django.contrib import admin

from .models import LabExam

admin.site.register(LabExam)
	  
```
## Running the server and doing CRUD operations
- Run the server
	> python manage.py runserver
```
Watching for file changes with StatReloader
Performing system checks...

System check identified no issues (0 silenced).
February 25, 2021 - 02:36:57
Django version 3.1.7, using settings 'bhola_lab.settings'
Starting development server at http://127.0.0.1:8000/
Quit the server with CONTROL-C.
```
- Go to http://127.0.0.1:8000/admin
- Login with admin credentials and manage some crud operations on lab_exam

# Pushing the project to github
## Creating a repository
- Login to github and create repository named as Ecommerce_Assignment_SIDDHANT_BASTOLA
## Adding remote repo 
```
git remote add origin https://github.com/sidhantbas/Ecommerce_Assignment_SIDDHANT_BASTOLA.git
```

```
	git add .
```
```
	git commit -m "First Commit for Lab Exam"
```
```
	git push 
```
## Creating a readme.md file and push changes
- Create a file readme.md inside project root folder
- add this file in stating area
- commit the change
- push to github






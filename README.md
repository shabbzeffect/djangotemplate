# djangotemplate

python -m venv myenv
cd myenv
.\scripts\activate
python –version
pip install Django
django-admin startproject practice
cd practice
python manage.py runserver
django-admin startapp myapp


Understanding Models in Django (Database)

myapp→ models.py
from django.db import models


class Student(models.Model):
   name = models.CharField(max_length=50)
   age = models.IntegerField()
   city = models.CharField(max_length = 50)

python manage.py makemigrations
python manage.py sqlmigrate myapp 0001
python manage.py migrate

Start Interactive Mode: python manage.py shell

✅ Adding a New Record
from myapp.models import Student  
student = Student(name="Priya", age=22)  # Create an object
student.save()  # Save to the database
📌 This will insert a new student Priya into the database.


✅ Fetch All Records
students = Student.objects.all()
print(students)
📌 Retrieves all records from the Student table.


✅ Fetch a Single Record
student = Student.objects.get(id=1)


python manage.py createsuperuser
print(student.name, student.age)
📌 Retrieves the student whose id = 1.

✅ Filter Records Based on Conditions
students = Student.objects.filter(age=22)  # Get students aged 22

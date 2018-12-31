Following Django tutorial

at step
https://docs.djangoproject.com/en/2.1/intro/tutorial07/

Create and activate a virtualenv (probably in ~/venvs or ~/virtualenvs):

    python3.6 -m venv django-tutorial
    source django-tutorial/bin/activate

Install dependencies:

    pip install -r requirements.txt


Confirm Django was installed:

    python -m django --version


Run app:

    python manage.py runserver


http://127.0.0.1:8000/polls/




Remember to create admin user and add some questions when starting from a fresh database:

    python manage.py createsuperuser

Since this is a totally fake example,
User: admin
Password: password
http://127.0.0.1:8000/admin/

As of current progress in tutorial, choices need to be added manually using the object API:

    python manage.py shell -i ipython

    from polls.models import Choice, Question
    q = Question.objects.get(pk=1)
    q.choice_set.create(choice_text='The sky', votes=0)

it's a boilerplate with common features for django.

secured secret key and database info (if you have more sensitive data in your settings.py, add them too.)
    what I did for this 
    'pip install django-environ'
    in your settings.py 'import environ'
    then 'env = environ.ENV()'
    and 'environ.Env.read_env()'
    then I made a .env file in the same folder of settings.py and set these variables:
        A. SECRET_KEY    (ex: SECRET_KEY=yoursecretkey)
        B. DATABASE_NAME (ex: DATABASE_NAME=postgresdatabase)
        C. DATABASE_USER (ex: DATABASE_USER=yourdatabaseusername)
        D. DATABASE_PASS (ex: DATABASE_PASS=yourpassword)
    no need for '' in these variables.
    in the settings.py:
        A. SECRET_KEY = env('SECRET_KEY')
        in the DATABASES section:
        B. 'NAME': env('DATABASE_NAME')
        C. 'USER': env('DATABASE_USER')
        D. 'PASSWORD': env('DATABASE_PASS')
    remember you need to make .env file yourself and set that 4 variables in the .env file too.
    if you have more sensitive data in your settings.py like email and ..., add them too.


installed accounts app, so you can edit your user model anytime you need in your project.
    in most projects we need to change user model fields, and when we reach to that point, you need either make 1to1 table or use abstract user like I did.
    this account app is made to give you the ability to make those changes anytime you need.
    account app is used abstract user idea.


static and media files already prepared both in urls.py and settings.py.
    you need to create media directory in the root. the templates directory already created.
    the static directory is placed in the config directory. you can put your static data in there, like bootstrap, style and ... .
    

the templates structured the way I like it but you can change that if you don't.
    the structure of templates is based on idea of having multiple themes.

how to use this:
    A. clone the repository
        git clone https://github.com/masoodshams/django_boilerplate.git
    B. change project name to anything you want to make. use find and replace and change the name in all of you files (about 15 times in 9 files including readme.).
    C. create your own virtual environment.
        python3 -m venv venv
    D. activate your venv.
        in windows: venv/Script/activate
    E. install requirements:
        pip install -r requirements.txt
    F. create your postgres database (if you want to use another DB, change your engine in settings.py )
    G. set the database info in the .env file (explained above)
    H. generate a new secret key and set that in .env file. 
    I. make migrations and migrate
        python manage.py makemigrations
        python manage.py migrate
    J. create new superuser:
        python manage.py createsuperuser
    K. make sure everything is fine:
        python manage.py runserver
        open your browser and go to http://127.0.0.1:8000/accounts/
        it should show USER PANEL in blue
        showing user panel means your urls and templates are ok, and showing in blue means your static files are ok.
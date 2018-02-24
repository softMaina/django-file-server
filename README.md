Django  file server
==================================

Minimalistic password-protected file server powered by Django.

The project contains source code from [Django file upload example at https://github.com/axelpale/minimal-django-file-upload-example) and [Authentication to Django websites https://github.com/narenaryan/django-auth-pattern]

Production setup serves behind [ nginx + gunicorn https://www.digitalocean.com/community/tutorials/how-to-set-up-django-with-postgres-nginx-and-gunicorn-on-ubuntu-16-04] you can obviously change it to whatever you fancy.


Django 1.11 is supported. Tested on Ubuntu 16.04 and Python 2.7
------------------

Initial setup:

    sudo apt-get -y install python-pip nginx
    git clone https://github.com/kindkaktus/django-file-server
    cd django-file-server
    sudo pip install --upgrade pip
    sudo pip install -r requirements.txt
    sudo -u www-data ./manage.py migrate
    sudo -u www-data ./manage.py createsuperuser

To run development server:

    sudo ./manage.py runserver 0.0.0.0:80  --settings=django_file_server.settings_devel

Finally, setup production server (nginx -> gunicorn -> django app):

   sudo ./install sh

Checks:

    ./manage.py check --deploy


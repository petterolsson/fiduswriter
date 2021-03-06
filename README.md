Fidus Writer 
===========

Fidus Writer is an online collaborative editor especially made for academics who need to use citations and/or formulas. The editor focuses on the content rather than the layout, so that with the same text, you can later on publish it in multiple ways: On a website, as a printed book, or as an ebook. In each case, you can choose from a number of layouts that are adequate for the medium of choice.


Contributing
----

For details on contributing, please check http://fiduswriter.com/help-us/


License
----

All of Fidus Writer's original code is licensed under the GNU AFFERO GENERAL PUBLIC LICENSE, for details see LICENSE. Some third party libraries are licensed under other, compatible open source libraries. Licensing information is included in those files.


Howto install
----

The following are instructions working on most *NIX systems.

0. Install the development packages of libjpeg and python and the python virtual environment creator. How you do this depends on your system. On Debian and Ubuntu the packages are called libjpeg-dev, python-dev and python-virtualenv. Install them with your favorite package manager, for example on the command line by running:

  sudo apt-get install libjpeg-dev python-dev python-virtualenv

1. Start the command line (terminal).

2. Cd to where you have your sources.

3. You can use the virtualenv command to create virtual environments. The following command will create an environment called "fiduswriter-venv":

  virtualenv  --no-site-packages fiduswriter-venv

4. Activate the virtualenv by typing:

  source fiduswriter-venv/bin/activate

5. Install the requirements for running  fiduswriter by typing:

  pip install -r requirements.txt

6. Synchronize the DB and create a superuser by typing:

  python manage.py syncdb

  python manage.py migrate

  python manage.py loaddata bibliography/fixture/initial_bib_rules.json

7. Run the fiduswriter server by typing:

  python manage.py runserver

  or, to start the server with external access, run:

  python manage.py runserver 0.0.0.0:8000

8. Navigate to "http://localhost:8000/admin/socialaccount/socialapp/add/"

9. Add at least one social app for Facebook. If you do not have actual Facebook app credentials, use the following data and save:

  Provider: Facebook
  
  Name: Facebook
  
  Client id: 1
  
  Secret: 1
  
  Sites: example.com

  If you have given external access to your server above, you will also need to add the external address of your server to the Facebook socialapp settings.
- - - - - -

For best results for the end user:

1. Install Chrome/Chromium at least version 26

2. Enable Webkit experimental features (in type "about:flags" into the navigation bar of the browser)

3. Restart Chrome/Chromium

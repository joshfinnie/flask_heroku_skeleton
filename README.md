Flask Heroku Skeleton
=====================

Getting the Base Code
---------------------

Clone this repo:

    $ git clone git@github.com:joshfinnie/flask_heroku_skeleton.git name-of-app/
    $ cd name-of-app

Install Prerequisites

    $ sudo easy_install pip
    $ sudo pip install virtualenv
    $ sudo gem install foreman heroku (http://devcenter.heroku.com/articles/using-the-cli)

Setting Application Up
----------------------

    $ mv flask-app-name/ name-of-app/
    $ perl -p -i -e "s/flask-app-name/name-of-app/g" `find . `

Running Locally
---------------

    $ virtualenv env
    $ source env/bin/activate
    $ pip install -r requirements.txt
    $ foreman start -p 8000  (-p is optional for port)


Deploying to Heroku
-------------------

    $ heroku create <app_name> -s cedar
    $ git push heroku master
    $ heroku scale web=1
    $ heroku ps
    $ heroku open


Using Custom Domains
--------------------

    $ heroku addons:add custom_domains
    $ heroku domains:add www.mydomainname.com
    $ heroku domains:add mydomainname.com (http://devcenter.heroku.com/articles/custom-domains)

Add the following A records to your DNS management tool.

    75.101.163.44
    75.101.145.87
    174.129.212.2

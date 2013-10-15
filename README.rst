Python-on-dotcloud custom service
---------------------------------

This is a beta version of the custom python service on dotCloud. Feel free to
use, but keep your eyes open for issues. If you find any issues please report
them.


How to use
----------
Clone this repo and use it as a base for your custom service. You will need to
replace the ``wsgi.py`` file with your own, and make sure you add all of your
application files. Don't change the ``builder`` or ``postinstall`` scripts
unless you know what you are doing, or else you could break it.


Things to watch out for
-----------------------
- Make sure that your ``python/builder``, ``python/uwsgi.sh``, ``postinstall``,
and ``wsgi.py`` scripts have execute permissions
- The virtualenv should be activated for you in the `postinstall` script, but
if not, then you will need to use the fully qualified path of the python binary
to make sure you have access to all of the files installed into your virtualenv.
``/home/dotcloud/env/bin/python`` or ``~/env/bin/python`` should work just fine.


Why use this service
--------------------
If the generic python service doesn't do what you need, you can use this
service to customize the python service to do what you need. The most requested
feature is the ability to change the uwsgi configuration. If you want to do
that you just need to change the ``uwsgi.sh`` file.


Python Version
--------------
This custom service supports 1 compiled version of python (3.3). The current
versions of python is 3.3.2.


You will also need to make sure you have your ``wsgi.py`` is setup correctly.
If you don't have it setup correctly then newrelic won't be able to gather
data correctly. See these pages at NewRelic for more information.

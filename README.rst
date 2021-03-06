===============================
PySugarCRM
===============================

.. image:: https://img.shields.io/travis/Feverup/pysugarcrm.svg
        :target: https://travis-ci.org/Feverup/pysugarcrm

.. image:: https://img.shields.io/pypi/v/pysugarcrm.svg
        :target: https://pypi.python.org/pypi/pysugarcrm


Python API Wrapper for SugarCRM v10

* Free software: BSD license
* Documentation: https://pysugarcrm.readthedocs.org.

Quickstart
------------

.. code-block :: bash

    $ pip install pysugarcrm


.. code-block :: python

    from pysugarcrm import SugarCRM
    api = SugarCRM('https://yourdomain.sugaropencloud.eu', 'youruser', 'yourpassword')

    # Return info about current user
    api.me

    # A more complex query requesting employees
    api.get('/Employees', query_params={'max_num': 2, 'offset': 2, 'fields': 'user_name,email'})

    {u'next_offset': 4,
     u'records': [{u'_acl': {u'fields': {}},
       u'_module': u'Employees',
       u'date_modified': u'2015-09-09T13:40:32+02:00',
       u'email': [{u'email_address': u'John.doe@domain.com',
         u'invalid_email': False,
         u'opt_out': False,
         u'primary_address': True,
         u'reply_to_address': False}],
       u'id': u'12364218-7d79-80e0-4f6d-35ed99a8419d',
       u'user_name': u'john.doe'},
      {u'_acl': {u'fields': {}},
       u'_module': u'Employees',
       u'date_modified': u'2015-09-09T13:39:54+02:00',
       u'email': [{u'email_address': u'alice@domain.com',
         u'invalid_email': False,
         u'opt_out': False,
         u'primary_address': True,
         u'reply_to_address': False}],
       u'id': u'a0e117c0-9e46-aebf-f71a-55ed9a2b4731',
       u'user_name': u'alice'}]}

Features
--------

* OAuth2 authentication with username and password

TODO
----

* Write methods to modify data in SugarCRM
* Add more auxiliary methods/properties
* Build documentation

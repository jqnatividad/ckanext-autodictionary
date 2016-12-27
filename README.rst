.. You should enable this project on travis-ci.org and coveralls.io to make
   these badges work. The necessary Travis and Coverage config files have been
   generated for you.

.. image:: https://travis-ci.org/jqnatividad/ckanext-autodictionary.svg?branch=master
    :target: https://travis-ci.org/jqnatividad/ckanext-autodictionary

.. image:: https://coveralls.io/repos/jqnatividad/ckanext-autodictionary/badge.svg
  :target: https://coveralls.io/r/jqnatividad/ckanext-autodictionary

.. image:: https://pypip.in/download/ckanext-autodictionary/badge.svg
    :target: https://pypi.python.org/pypi//ckanext-autodictionary/
    :alt: Downloads

.. image:: https://pypip.in/version/ckanext-autodictionary/badge.svg
    :target: https://pypi.python.org/pypi/ckanext-autodictionary/
    :alt: Latest Version

.. image:: https://pypip.in/py_versions/ckanext-autodictionary/badge.svg
    :target: https://pypi.python.org/pypi/ckanext-autodictionary/
    :alt: Supported Python versions

.. image:: https://pypip.in/status/ckanext-autodictionary/badge.svg
    :target: https://pypi.python.org/pypi/ckanext-autodictionary/
    :alt: Development Status

.. image:: https://pypip.in/license/ckanext-autodictionary/badge.svg
    :target: https://pypi.python.org/pypi/ckanext-autodictionary/
    :alt: License

=============
ckanext-autodictionary
=============

.. Put a description of your extension here:
   What does it do? What features does it have?
   Consider including some screenshots or embedding a video!

Automatically create data dictionaries for all datastore objects. This extension leverages Postgres' native
system catalog tables to pre-populate the data dictionary and also makes use of Postgres' native `COMMENT <https://www.postgresql.org/docs/9.6/static/sql-comment.html>`_
command to add a user-friendly field name and description.

------------
Requirements
------------

* CKAN 2.5+
* CKAN Datastore


------------
Installation
------------

.. Add any additional install steps to the list below.
   For example installing any non-Python dependencies or adding any required
   config settings.

To install ckanext-autodictionary:

1. Activate your CKAN virtual environment, for example::

     . /usr/lib/ckan/default/bin/activate

2. Install the ckanext-autodictionary Python package into your virtual environment::

     pip install ckanext-autodictionary

3. Add ``autodictionary`` to the ``ckan.plugins`` setting in your CKAN
   config file (by default the config file is located at
   ``/etc/ckan/default/production.ini``).

4. Restart CKAN. For example if you've deployed CKAN with Apache on Ubuntu::

     sudo service apache2 reload


---------------
Config Settings
---------------

Document any optional config settings here. For example:

* Include `pg_stats <https://www.postgresql.org/docs/9.3/static/view-pg-stats.html>`_ view info
    
    # Include descriptive statistics from pg_stats view
    # (optional, default: false).
    ckanext.autodictionary.include_stats = true

* Show related tables (i.e. tables that have columns with the same name)

    # show related tables
    # (optional, default: false)
    ckanext.autodictionary.show_related_tables = true


------------------------
Development Installation
------------------------

To install ckanext-autodictionary for development, activate your CKAN virtualenv and
do::

    git clone https://github.com/jqnatividad/ckanext-autodictionary.git
    cd ckanext-autodictionary
    python setup.py develop
    pip install -r dev-requirements.txt


-----------------
Running the Tests
-----------------

To run the tests, do::

    nosetests --nologcapture --with-pylons=test.ini

To run the tests and produce a coverage report, first make sure you have
coverage installed in your virtualenv (``pip install coverage``) then run::

    nosetests --nologcapture --with-pylons=test.ini --with-coverage --cover-package=ckanext.autodictionary --cover-inclusive --cover-erase --cover-tests


---------------------------------
Registering ckanext-autodictionary on PyPI
---------------------------------

ckanext-autodictionary should be availabe on PyPI as
https://pypi.python.org/pypi/ckanext-autodictionary. If that link doesn't work, then
you can register the project on PyPI for the first time by following these
steps:

1. Create a source distribution of the project::

     python setup.py sdist

2. Register the project::

     python setup.py register

3. Upload the source distribution to PyPI::

     python setup.py sdist upload

4. Tag the first release of the project on GitHub with the version number from
   the ``setup.py`` file. For example if the version number in ``setup.py`` is
   0.0.1 then do::

       git tag 0.0.1
       git push --tags


----------------------------------------
Releasing a New Version of ckanext-autodictionary
----------------------------------------

ckanext-autodictionary is availabe on PyPI as https://pypi.python.org/pypi/ckanext-autodictionary.
To publish a new version to PyPI follow these steps:

1. Update the version number in the ``setup.py`` file.
   See `PEP 440 <http://legacy.python.org/dev/peps/pep-0440/#public-version-identifiers>`_
   for how to choose version numbers.

2. Create a source distribution of the new version::

     python setup.py sdist

3. Upload the source distribution to PyPI::

     python setup.py sdist upload

4. Tag the new release of the project on GitHub with the version number from
   the ``setup.py`` file. For example if the version number in ``setup.py`` is
   0.0.2 then do::

       git tag 0.0.2
       git push --tags

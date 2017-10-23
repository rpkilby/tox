
tox3 test fork
==============

.. image:: https://img.shields.io/pypi/v/tox3.svg
   :target: https://pypi.org/project/tox3/
.. image:: https://img.shields.io/pypi/pyversions/tox3.svg
  :target: https://pypi.org/project/tox3/
.. image:: https://travis-ci.org/rpkilby/tox3.svg?branch=tox3
    :target: https://travis-ci.org/rpkilby/tox3

Official tox project: https://github.com/tox-dev/tox

What is tox3?
-------------

tox3 is a test fork of tox that uses python 3's builtin ``venv`` module (instead of ``virtualenv``) to build test
environments. ``virtualenv`` is historically python 2/3 compatible, however it ships some files that are pinned at
their python 2.6 version, such as the ``site`` module (see: pypa/virtualenv#355). These incompatibilities are just
deprecation warnings for now, but they will eventually become errors.

How to use?
-----------

* Uninstall ``tox``
* Install ``tox3``
* Clear your ``.tox/``  working directory
* Run ``tox`` as normal

What's here?
------------

This fork contains two branches:

* ``py3-venv`` is the branch for the pull request (tox-dev/tox#630)
* ``tox3`` is the release branch, based off of ``py3-venv``. It contains changes not relevant to the PR, such as a
  simplified CI config, project setup, etc...

Update process
--------------

Here's how tox3 is kept up-to-date:

* Wait for someone to tell me that tox3 is out-of-date
* Update ``master`` from upstream tox-dev/tox
* Rebase ``py3-venv`` onto ``master``
* Rebase ``tox3`` onto ``py3-venv``
* Cut new release

Docker-MySQLTuner
=================

|dockerpulls|

Description
-----------

Provides a docker container for the MySQLtuner script. The container is based
on Alpine Linux, so it should be obnoxiously small.

Note that I am not the maintainer of ``mysqltuner`` itself; please report any
issues with the tool `upstream`_.

You can find the source code in `this Github repo`_.

Usage
-----

Treat this image as if it were the mysqltuner binary. So

.. code-block:: console

    $ docker run --rm -it thekevjames/mysqltuner --buffers --cvefile /vulnerabilities.csv

For full usage information, see the `MySQLTuner Homepage`_.

Releasing
---------

Whenever a new release of MySQLTuner is pushed, this library is updated
accordingly:

.. code-block:: console

    $ local version="1.7.15"
    $ for file in vulnerabilities.csv basic_passwords.txt mysqltuner.pl; do
        $ wget "https://raw.githubusercontent.com/major/MySQLTuner-perl/${version}/${file}" -O "./root/${file}"
    $ done

.. _MySQLTuner Homepage: http://mysqltuner.pl/
.. _this Github repo: https://github.com/TheKevJames/tools/tree/master/docker-mysqltuner
.. _upstream: https://github.com/major/MySQLTuner-perl

.. |dockerpulls| image:: https://img.shields.io/docker/pulls/thekevjames/mysqltuner.svg?style=flat-square
    :alt: Docker Pulls
    :target: https://hub.docker.com/r/thekevjames/mysqltuner/

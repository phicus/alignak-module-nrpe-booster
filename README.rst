Alignak Web services Module
===========================

*Alignak Web services module*

Build status (stable release)
-----------------------------

.. image:: https://travis-ci.org/Alignak-monitoring-contrib/alignak-module-ws.svg?branch=master
    :target: https://travis-ci.org/Alignak-monitoring-contrib/alignak-module-ws


Build status (development release)
----------------------------------

.. image:: https://travis-ci.org/Alignak-monitoring-contrib/alignak-module-ws.svg?branch=develop
    :target: https://travis-ci.org/Alignak-monitoring-contrib/alignak-module-ws


Short description
-----------------

This module allows Alignak Pollers to bypass the launch of the check_nrpe process.
It reads the check command and opens the connection by itself.
It scales the use of NRPE for active supervision of servers hosting NRPE agents.


Installation
------------

Requirements
~~~~~~~~~~~~
To use NRPE/SSL install `pyOpenssl` Python wrapper module with the OpenSSL library.


From PyPI
~~~~~~~~~
To install the module from PyPI:
::

    pip install alignak-module-nrpe-booster


From source files
~~~~~~~~~~~~~~~~~
To install the module from the source files:
::

    git clone https://github.com/Alignak-monitoring-contrib/alignak-module-nrpe-booster
    cd alignak-module-nrpe-booster
    pip install -r requirements
    python setup.py install


Configuration
-------------

Once installed, this module has its own configuration file in the */usr/local/etc/alignak/arbiter/modules* directory.
The default configuration file is *mod-nrpe-booster.cfg*. No configuration is necessary for this module.

Configure an Alignak poller to use this module:

    - edit your poller daemon configuration file
    - add the `module_alias` parameter value (`nrpe_booster`) to the `modules` parameter of the daemon

Tag the NRPE commands with the `module_type` parameter::

    define command {
        command_name   check_nrpe
        command_line   $USER1$/check_nrpe -H $HOSTADRESS$ -c $ARG1$ -a $ARG2$
        module_type    nrpe_poller
    }



Bugs, issues and contributing
-----------------------------

Please report any issue using the project `GitHub repository: <https://github.com/Alignak-monitoring-contrib/alignak-module-ws/issues>`_.

License
-------

Alignak Module External commands is available under the `GPL version 3 license`_.

.. _GPL version 3 license: http://opensource.org/licenses/GPL-3.0
.. _Alignak monitoring contrib: https://github.com/Alignak-monitoring-contrib
.. _PyPI repository: <https://pypi.python.org/pypi>
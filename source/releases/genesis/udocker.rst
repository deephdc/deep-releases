udocker
=======

.. contents:: Table of Contents

**udocker** is a basic user tool to execute simple docker
containers in user space without requiring root privileges.
Enables download and execution of docker containers by
non-privileged users in Linux systems where docker is not
available. It can be used to pull and execute docker
containers in Linux batch systems and interactive clusters
that are managed by other entities such as grid infrastructures
or externally managed batch or interactive systems.

**udocker** does not require any type of privileges nor the
deployment of services by system administrators. It can be
downloaded and executed entirely by the end user.

**udocker** is a wrapper around several tools to mimic a
subset of the docker capabilities including pulling images
and running containers with minimal functionality.

Release Notes
-------------

.. toctree::
   :maxdepth: 1
   :glob:

   udocker/*

Documentation
-------------

Detailed documentation can be found at:

* `GitBook Guide <https://indigo-dc.gitbooks.io/udocker/content/>`_
* `GitHub documentation <https://github.com/indigo-dc/udocker/tree/master/doc>`_

Support
-------

* GitHub issues:
    * https://github.com/indigo-dc/udocker/issues
* DEEP project’s internal support ticketing system: https://jira.deep-hybrid-datacloud.eu/





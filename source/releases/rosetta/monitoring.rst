Monitoring
=======

.. contents:: Table of Contents

The **Monitoring Framework** is a set of tools which allow performing 
several monitoring operations in the platform resulting from the 
INDIGO-Datacloud project (https://www.indigo-datacloud.eu/). 
The Monitoring Framework is based on Zabbix, as the collector of the 
monitoring information coming from different sources, due to its maturity, 
its community support and its flexibility for different environments.
The Monitoring Framework is divided in several main parts:
* The Zabbix server (with the corresponding configuration and some support scripts);
* The Zabbix wrapper, created for enabling a REST API for Zabbix;
* Several probes, with different monitoring purposes (OCCI, Heapster, etc.).

This repository contains the supporting scripts for the Zabbix server (in order to 
perform automatic backups of the Zabbix database and configuration), the wrapper to be 
deployed with Zabbix (as a way to facilitate integration) and the probes released in the 
first version: a probe for monitoring OCCI interfaces of Infrastructure Providers and a 
probe for monitoring the Kubernetes cluster where the Indigo platform is deployed (by 
means of the Heapster tool).

Release Notes
-------------

.. toctree::
   :maxdepth: 1
   :glob:

   monitoring/*

Documentation
-------------

Detailed documentation can be found at:

* `GitHub documentation <https://github.com/indigo-dc/Monitoring/blob/master/README.md>`_

Support
-------

* GitHub issues:
    * https://github.com/indigo-dc/Monitoring/issues
* DEEP project’s internal support ticketing system: https://jira.deep-hybrid-datacloud.eu/
* Main develoeprs:
    * jose.sanchezm@atos.net
    * rut.palmero@atos.net
    * damian.kaliszan@man.poznan.pl






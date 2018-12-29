PaaS Orchestrator
=================

.. contents:: Table of Contents

The **INDIGO PaaS Orchestrator** is a component of the PaaS layer that allows to
instantiate resources on Cloud Management Frameworks (like `OpenStack <https://www.openstack.org/>`_ and `OpenNebula <http://opennebula.org/>`_ )
and `Mesos <http://mesos.apache.org/>`_ clusters.

It takes the deployment requests, expressed through templates written in
`TOSCA YAML Simple Profile v1.0 <http://docs.oasis-open.org/tosca/TOSCA-Simple-Profile-YAML/v1.0/TOSCA-Simple-Profile-YAML-v1.0.html>`_,
and deploys them on the best cloud site available. In order to do that

* it gathers SLAs, monitoring info and other data from other platform services,
* it asks to the cloud provider ranker for a list of the best cloud sites.


Release Notes
-------------

.. toctree::
   :maxdepth: 1
   :glob:

   paas-orchestrator/*

Documentation
-------------

Detailed documentation is available at:

* `GitHub README <https://github.com/indigo-dc/orchestrator/blob/v2.1.1-FINAL/README.md>`_
* `GitBook Guides <https://indigo-dc.gitbooks.io/indigo-paas-orchestrator/content/>`_

Support
-------

* GitHub issues: https://github.com/indigo-dc/orchestrator/issues
* DEEP project’s internal support ticketing system: http://jira.deep-hybrid-datacloud.eu/



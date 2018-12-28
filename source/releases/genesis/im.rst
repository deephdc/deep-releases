Infrastructure Manager
======================

.. contents:: Table of Contents

**IM** is a tool that deploys complex and customized virtual infrastructures
on IaaS Cloud deployments (such as AWS, OpenStack, etc.). It eases the access
and the usability of IaaS clouds by automating the VMI (Virtual Machine Image)
selection, deployment, configuration, software installation, monitoring and
update of the virtual infrastructure. It supports APIs from a large number
of virtual platforms, making user applications cloud-agnostic. In addition
it integrates a contextualization system to enable the installation and configuration
of all the user required applications providing the user with a fully functional infrastructure.

This version evolved in the projects `INDIGO-Datacloud <https://www.indigo-datacloud.eu/>`_ and
`DEEP – Hybrid DataCloud <https://deep-hybrid-datacloud.eu/>`_. It is used by the **INDIGO Orchestrator**
to contact Cloud sites to finally deploy the VMs/containers.

Release Notes
-------------

.. toctree::
   :maxdepth: 1
   :glob:

   im/*

Documentation
-------------

Detailed documentation can be found at:

* `GitHub README <https://github.com/indigo-dc/im/blob/master/README.md>`_
* `IM ReadTheDocs <https://imdocs.readthedocs.io/en/latest/>`_
* `Ansible Role for IM <https://github.com/indigo-dc/im/blob/master/ansible_install.yaml>`_

Support
-------

Through:

* GitHub issues: https://github.com/indigo-dc/im/issues
* DEEP project’s internal support ticketing system: http://jira.deep-hybrid-datacloud.eu/

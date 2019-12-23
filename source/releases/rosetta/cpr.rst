CloudProviderRancher
=======

.. contents:: Table of Contents

**Orchent** is a command line application to manage deployments
and their resources through the `PaaS Orchestrator <https://indigo-dc.gitbooks.io/indigo-paas-orchestrator/content/>`_ in a fast and easy way.

The **Cloud Provider Ranker** is a standalone REST WEB Service which ranks cloud provider 
services using rules implemented with the Drools framework. The **INDIGO PaaS Orchestrator**
 interacts with this service in order to obtain the rank of two or more cloud services 
 depending on the match with specific rules.
The aim of this micro component is to fully decouple the ranking logic from the 
Orchestrator's business logic.

Release Notes
-------------

.. toctree::
   :maxdepth: 1
   :glob:

   cpr/*

Documentation
-------------

Detailed documentation is available at:

* `GitHub README <https://github.com/indigo-dc/CloudProviderRanker/blob/master/README.md>`_
* `GitBook Guides <https://indigo-dc.gitbook.io/cloud-provider-ranker/>`_

Support
-------

* GitHub issues: https://github.com/indigo-dc/CloudProviderRanker/issues
* DEEP project’s internal support ticketing system: http://jira.deep-hybrid-datacloud.eu/




CloudInfoProvider-DEEP
======================

.. contents:: Table of Contents

The **Cloud Information Provider** generates a representation of
cloud resources, that can be published inside a BDII (using the
provided LDIF templates for a GlueSchema v2 representation) or
any other component like the INDIGO Configuration Management
Database (CMDB) (Using specific templates).

The generated representation is described using a `Mako  <http://www.makotemplates.org/>`_ template
having access to the cloud middleware information.

The current document describe the main features implemented
for the Cloud Information Provider under the DEEP-Hybrid-Datacloud project.

Main documentation for the product is maintained `upstream <https://github.com/EGI-Foundation/cloud-info-provider>`_, including usage and contribution (for developers)
guidelines. The documentation for the features pending to be merged
upstream and/or specific to DEEP-Hybrid-Datacloud will be added below,
associated with the release version.

Release Notes
-------------

.. toctree::
   :maxdepth: 1
   :glob:

   cip-deep/*

Documentation
-------------

Detailed documentation is available at:

* https://github.com/EGI-Foundation/cloud-info-provider

Documentation specific for the DEEP-HDC vesion is available at:

* https://github.com/indigo-dc/cloud-info-provider-deep/blob/DEEP/README-DEEP.md


Support
-------

- GitHub issues: https://github.com/EGI-Foundation/cloud-info-provider/issues?q=is%3Aissue+is%3Aclosed
- DEEP project’s internal support ticketing system: http://jira.deep-hybrid-datacloud.eu/
- EGI GGUS Support Unit: https://wiki.egi.eu/wiki/GGUS:EGI_Cloud_Information_Discovery_FAQ


DEEP-1 Genesis
==============

The `DEEP - HybridDataCloud <https://deep-hybrid-datacloud.eu/>`__
project is pleased to announce the general availability of its **first
public software release**, codenamed **Genesis**

This release …

Included components
-------------------

.. toctree::
   :maxdepth: 1

   a4c-deep
   cip-deep
   daas
   im
   orchent
   paas-orchestrator
   ttt
   udocker
   indigovr


Highlights
----------


Key technical highlights:

-  Alien4Cloud-DEEP plugin

   -  Suppor for visual composition of TOSCA templates PaaS orchestrator
      support

-  cloud-info-provider

   -  Support for GPU and Infibinand resources

-  DEEPaaS API

   -  Support for training a machine learning application Support for
      performing inferences/analisys/predictions Support only for
      synchronous requests
   -  OpenID Connect support
   -  Support for standalone service & OpenWhisk action

-  Infrastructure Manager (IM)

   -  Improved support for hybrid deployments Support for additional
      TOSCA types

-  PaaS Orchestrator

   -  Hybrid deployments on multiple sites
   -  Support to specifying specialized computing hardware Improved
      support for deployment failures

-  uDocker

   -  Improved support for GPUs and Infiniband

-  Visual application topology composition and deployment

   -  Graphical composition of complex application topologies
   -  Deployment through PaaS orchestrator

-  DEEP as a Service

   -  Deployment of DEEP Open Catalog components as server-less
      functions

-  `DEEP Open Catalog <http://marketplace.deep-hybrid-datacloud.eu/>`__

   -  Ready-to-use machine learning and deep learning applications,
      including:

      -  Machine learning frameworks + JupyterLab
      -  Machine learning ready to use models
      -  Deep learning ready to use models
      -  BigData analytic tools

Release Notes
-------------

The DEEP-1/Genesis release consists in 9 Products and a number of technical guides:

-  13 OS packages, for CentOS 7 and Ubuntu 16.04

   -  6 RPMS & SRPMS
   -  4 binary & source DEBS
   -  3 tarballs

-  5 Docker containers


You can find in the later sections the full list of products, with
detailed release notes and instructions for their
installation/configuration.

Installation Notes
------------------

All DEEP - HybridDataCloud products are distributed from standard
OperatingSystems (OS) repositories and DockerHub registry of the `indigodatacloud <https://cloud.docker.com/u/indigodatacloud/repository/list>`_ organization.

The packages repositories have the following structure:

* DEEP-HDC production (stable):

  * `deep-hdc/production/{1,2}/centos7/x86_64/{base|updates} <http://repo.indigo-datacloud.eu/repository/deep-hdc/production/1/centos7/x86_64/base/repoview/>`_

    * containing signed, well tested software components

  * Third-party: `deep-hdc/production/{1,2}/centos7/x86_64/third-party <http://repo.indigo-datacloud.eu/repository/deep-hdc/production/1/centos7/x86_64/third-party/>`_

    * containing packages that are not part of DEEP, or not part of the base OS or EPEL, but used as dependencies by other DEEP components

* DEEP-HDC testing: `deep/testing/{1,2}/{centos7,ubuntu}/ <http://repo.indigo-datacloud.eu/repository/deep-hdc/testing/>`_

  * containing packages that will become part of the next stable distribution; in the certification and validation phase.

* DEEP-HDC preview: `deep/preview/{1,2}/{centos7,ubuntu}/ <http://repo.indigo-datacloud.eu/repository/deep-hdc/preview/>`_

  * containing signed packages that will become part of the next stable update,
      available for technical-previews

All packages are signed with the INDIGO - DataCloud gpg key. The public
key can be downloaded from
`here <http://repo.indigo-datacloud.eu/repository/RPM-GPG-KEY-indigodc>`__,
and the fingerprint from
`here <http://repo.indigo-datacloud.eu/repository/INDIGODC_key_fingerprint.asc>`__.

It is strongly recommended the use of the lastest version of the
**deep-release** packages containing the public key and the YUM and APT
repository files.

On the `DockerHub Registry <https://hub.docker.com/>`__, DEEP -
HybridDataCloud uses the INDIGO - DataCloud and DEEP-HDC Organizations:

* `indigodatacloud <https://hub.docker.com/u/indigodatacloud/dashboard/>`__, for Core Services
* `deephdc <https://hub.docker.com/u/deephdc/dashboard/>`__, for DEEP-OC modules

Containers present in those repositories and released in DEEP-1 are
tagged with “DEEP-1” tag and signed, leveraging the Docker’s trust
features so that users can pull trusted images.

To understand how to install and configure DEEP-1/Genesis services and
components either refer to the `Generic Installation and Configuration
Guide <https://add_generic>`__ chapter or to each individual product
documentation.

Software
--------

DEEP-1 software can be downloaded from `DEEP - HybridDataCloud
repositories <http://repo.indigo-datacloud.eu/repository/deep-hdc/>`__.

Documentation
-------------

Please find DEEP-1 documentation `here <https://releases.deep-hybrid-datacloud.eu/en/latest/>`__.

Support
-------

Most complex software contains bugs, we are not an exception. One of the
features of free and open source software is the ability to report bugs,
helping to fix or improve the software you use.

DEEP - HybridDataCloud project uses …

More details regarding each product support channels are provided in the
respective products release pages.

Developers, researchers and IT enthusiasts: feel free to write to
info@project to ask for more information on how to use DEEP solutions
for your work. For automatic notifications you can register to the DEEP
- HybridDataCloud release RSS feed or subscribe to the DEEP -
HybridDataCloud Announce Mailing list. You can also socialize with us
via Twitter, Facebook and join our LinkedIn group.

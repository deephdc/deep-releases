DEEP-1 Genesis
==============

The `DEEP - HybridDataCloud <https://deep-hybrid-datacloud.eu/>`__
project is pleased to announce the general availability of its **first
public software release**, codenamed **Genesis**

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

-  17 OS packages, for CentOS 7 and Ubuntu 16.04

   -  8 RPMS & SRPMS
   -  6 binary & source DEBS
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

* DEEP-HDC **production** (stable):

  * `deep-hdc/production/{1,2}/centos7/x86_64/{base|updates} <http://repo.indigo-datacloud.eu/repository/deep-hdc/production/1/centos7/x86_64/base/repoview/>`_
  * `deep-hdc/production/{1,2}/ubuntu/dists/xenial/main/{binary-amd64,source} <http://repo.indigo-datacloud.eu/repository/deep-hdc/production/1/ubuntu/dists/trusty/main/>`_

    * containing signed, well tested software components

  * third-party:

    * `deep-hdc/production/{1,2}/centos7/x86_64/third-party <http://repo.indigo-datacloud.eu/repository/deep-hdc/production/1/centos7/x86_64/third-party/>`_
    * `deep-hdc/production/{1,2}/ubuntu/dists/xenial/third-party{binary-amd64,source} <http://repo.indigo-datacloud.eu/repository/deep-hdc/production/1/ubuntu/dists/trusty/third-party>`_

      * containing packages that are not part of DEEP, or not part of the base OS or EPEL, but used as dependencies by other DEEP components

* DEEP-HDC **testing**: `deep/testing/{1,2}/{centos7,ubuntu}/ <http://repo.indigo-datacloud.eu/repository/deep-hdc/testing/>`_

  * containing packages that will become part of the next stable distribution; in the certification and validation phase.

* DEEP-HDC **preview**: `deep/preview/{1,2}/{centos7,ubuntu}/ <http://repo.indigo-datacloud.eu/repository/deep-hdc/preview/>`_

  * containing signed packages that will become part of the next stable update, available for technical-previews

All packages in production and preview repositories are signed with the INDIGO - DataCloud gpg key. The public
key can be downloaded from
`here <http://repo.indigo-datacloud.eu/repository/RPM-GPG-KEY-indigodc>`__,
and the fingerprint from
`here <http://repo.indigo-datacloud.eu/repository/INDIGODC_key_fingerprint.asc>`__.

Please import the key BEFORE starting!

* for CentOS7 save the key under /etc/pki/rpm-gpg/
.. code-block:: bash

    # rpm --import http://repo.indigo-datacloud.eu/repository/RPM-GPG-KEY-indigodc

* for Ubuntu:
.. code-block:: bash

    # wget -q -O - http://repo.indigo-datacloud.eu/repository/RPM-GPG-KEY-indigodc | sudo apt-key add -

Configuring the use of DEEP-HDC repositories
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

YUM & APT configuration files are available at:

* CentOS7 - http://repo.indigo-datacloud.eu/deep-hdc/repos/deep-1.repo
* Ubuntu 16.04 - http://repo.indigo-datacloud.eu/deep-hdc/repos/deep-1-ubuntu16_04.list

or use the deephdc-release package to install DEEP-HDC repositories:

* CentOS7:
.. code-block:: bash

    # wget http://repo.indigo-datacloud.eu/repository/deep-hdc/production/1/centos7/x86_64/base/deephdc-release-1.0.0-1.el7.centos.noarch.rpm
    # yum localinstall -y deep-release-1.0.0-1.el7.centos.noarch.rpm

* Ubuntu 16.04:
.. code-block:: bash

    # wget http://repo.indigo-datacloud.eu/repository/deep-hdc/1/ubuntu/dists/xenial/main/binary-amd64/deephdc-release_1.0.0-1_amd64.deb
    # dpkg -i deep-release_1.0.0-1_amd64.deb

These packages will install required dependencies, the INDIGO - DataCloud public key and ensures the precedence of DEEP-HybridDataCloud repositories over EPEL and Ubuntu.

It is strongly recommended the use of the lastest version of the
**deephdc-release** packages containing the public key and the YUM and APT
repository files.

Enable the DEEP-HDC Containers repositories
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

On the `DockerHub Registry <https://hub.docker.com/>`__, DEEP -
HybridDataCloud uses the INDIGO - DataCloud and DEEP-HDC Organizations:

* `indigodatacloud <https://hub.docker.com/u/indigodatacloud/dashboard/>`__, for Core Services
* `deephdc <https://hub.docker.com/u/deephdc/dashboard/>`__, for DEEP-OC modules

Containers present in those repositories and released in DEEP-1 major release are
tagged with “DEEP-1” tag and signed, leveraging the `Docker’s trust
features <https://docs.docker.com/engine/security/>`_ so that users can pull trusted images.

Currently, content trust is disabled by default. You must enable it by setting
the ``DOCKER_CONTENT_TRUST`` environment variable, like bellow:

.. code-block:: bash

  export DOCKER_CONTENT_TRUST=1

For more details regarding the "Content Trust in Docker" please read `Docker's Documentation <https://docs.docker.com/engine/security/trust/content_trust/>`_

Content trust is associated with the TAG portion of an image. For DEEP-1/Genesis
release the signed tag is DEEP-1. See example bellow if you want to ensure the correct use of DEEP-HDC images:

.. code-block:: bash

  $ export DOCKER_CONTENT_TRUST=1

  $ docker pull indigodatacloud/orchestrator:2.1.1-FINAL
  No trust data for 2.1.1-FINAL

  $ docker pull indigodatacloud/orchestrator:DEEP-1
  Pull (1 of 1): indigodatacloud/orchestrator:DEEP-1@sha256:441c8b037684422ccdf2fdec322c9c09904ed3ce74d9fcc7d2862a9f53ad36be
  sha256:441c8b037684422ccdf2fdec322c9c09904ed3ce74d9fcc7d2862a9f53ad36be: Pulling from indigodatacloud/orchestrator
  93857f76ae30: Pull complete
  [...]
  e8c92b40b492: Pull complete
  Digest: sha256:441c8b037684422ccdf2fdec322c9c09904ed3ce74d9fcc7d2862a9f53ad36be
  Status: Downloaded newer image for indigodatacloud/orchestrator@sha256:441c8b037684422ccdf2fdec322c9c09904ed3ce74d9fcc7d2862a9f53ad36be
  Tagging indigodatacloud/orchestrator@sha256:441c8b037684422ccdf2fdec322c9c09904ed3ce74d9fcc7d2862a9f53ad36be as indigodatacloud/orchestrator:indigo_2
  $ docker images
  REPOSITORY                     TAG                 IMAGE ID            CREATED             SIZE
  indigodatacloud/orchestrator   DEEP-1            bdbe758d9f32        37 hours ago        843MB

Documentation
-------------

Please find DEEP-1 documentation `here <https://releases.deep-hybrid-datacloud.eu/en/preview/releases/genesis/index.html#included-components>`__.

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

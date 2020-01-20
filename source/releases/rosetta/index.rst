DEEP-2 Rosetta
==============

The `DEEP - HybridDataCloud <https://deep-hybrid-datacloud.eu/>`__
project is pleased to announce the general availability of its **second
public software release**, codenamed **Rosetta**

Included components
-------------------

.. toctree::
   :maxdepth: 1

   a4c-deep
   cip-deep
   cpr
   daas
   im
   monitoring
   paas-orchestrator
   paas-dashboard
   sso
   indigovr


Highlights
----------


Key technical highlights:

 - Alien4Cloud-DEEP plugin

   - Support for the OpenStack normative TOSCA types, for the IndigoDC TOSCA custom types, for DEEP-OC templates
   - Outputs retrieval and display from the Indigo Orchestrator
   - IAM authentication support

 - DEEP-Hybrid-DataCloud Cloud Information Provider

   - Support for multitenancy in CMDBv1, for new Mesos providers, for fetching GPU information from OpenStack and Mesos

 - CloudProviderRanker

   - new release featuring a complete code re-engineered using Spring Boot framework and modified ranking algorithm
  
 - DEEPaaS API

   - New V2 version of the API, major change that is not backwards compatible, supporting async requests, following Swagger UI 3.X Specifications, with new options allowing to specify the number of workers that will be used for model operations

 -  Infrastructure Manager (IM)

   - new version with multiple bug fixes and enhancements, improving deployment of hybrid clusters. 


 -  INDIGO VirtualRouter

   - new verion with many bug fixes and improvements, supporting OpenStack

 - Monitoring Framework

   - first release through the DEEP-HDC project, providing improved versions of Openstack and Mesos probes and new QCG probe

 -  PaaS Orchestrator

   -  new version that add support for compute GPU, flavors and for vRouter deployment

 -  PaaS Orchestrator Dashboard

   -  first stable release with INDIGO-IAM authentication, allowing easier management of infrastructures deloyments

 -  Spring Social OIDC

   -  first release in DEEP-HDC allowing for the integration of the orchestrator functionality into Spring projects such as Alien4Cloud through Spring Social


Release Notes
-------------

The DEEP-2/Rosetta release consists in 10 Products and a number of
technical guides:

-  22 OS packages, for CentOS 7, Ubuntu 16.04, Ubuntu 18.04
-  6 Docker containers


You can find in the later sections the full list of products, with
detailed release notes and instructions for their
installation/configuration.

Installation Notes
------------------

All DEEP - HybridDataCloud products are distributed from standard
Operating Systems (OS) repositories and DockerHub registry of the
`indigodatacloud <https://hub.docker.com/orgs/indigodatacloud/repositories>`_ and `deephdcgo <https://hub.docker.com/orgs/deephdc/repositories>`_
organization.

The packages repositories have the following structure:

* DEEP-HDC **production** (stable):

  * `deep-hdc/production/2/centos7/x86_64/{base|updates} <http://repo.indigo-datacloud.eu/repository/deep-hdc/production/2/centos7/x86_64/base/repoview/>`_
  * `deep-hdc/production/2/ubuntu/dists/xenial/main/{binary-amd64,source} <http://repo.indigo-datacloud.eu/repository/deep-hdc/production/2/ubuntu/dists/>`_

    * containing signed, well tested software components

  * third-party:

    * `deep-hdc/production/2/centos7/x86_64/third-party <http://repo.indigo-datacloud.eu/repository/deep-hdc/production/1/centos7/x86_64/third-party/repoview>`_
    * `deep-hdc/production/2/ubuntu/dists/{xenial,bionic}/third-party{binary-amd64,source} <http://repo.indigo-datacloud.eu/repository/deep-hdc/production/2/ubuntu/dists/>`_

      * containing packages that are not part of DEEP, or not part of the base OS or EPEL, but used as dependencies by other DEEP components

* DEEP-HDC **testing**: `deep-hdc/testing/2/{centos7,ubuntu}/ <http://repo.indigo-datacloud.eu/repository/deep-hdc/testing/2>`_

  * containing packages that will become part of the next stable distribution; in the certification and validation phase.

* DEEP-HDC **preview**: `deep/preview/2/{centos7,ubuntu}/ <http://repo.indigo-datacloud.eu/repository/deep-hdc/preview/2>`_

  * containing signed packages that will become part of the next stable update, available for technical-previews

All packages in production and preview repositories are signed with the
INDIGO - DataCloud gpg key. The public key can be downloaded from
`here <http://repo.indigo-datacloud.eu/repository/RPM-GPG-KEY-indigodc>`__,
and the fingerprint from
`here <http://repo.indigo-datacloud.eu/repository/INDIGODC_key_fingerprint.asc>`__.

Please import the key BEFORE starting!

* for CentOS7 save the key under /etc/pki/rpm-gpg/
.. code-block:: bash

    # rpm --import https://repo.indigo-datacloud.eu/repository/RPM-GPG-KEY-indigodc

* for Ubuntu:
.. code-block:: bash

    # wget -q -O - https://repo.indigo-datacloud.eu/repository/RPM-GPG-KEY-indigodc | sudo apt-key add -

Configuring the use of DEEP-HDC repositories
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

YUM & APT configuration files are available at:

* CentOS7 - https://repo.indigo-datacloud.eu/deep-hdc/repos/deep-2.repo
* Ubuntu 16.04 - https://repo.indigo-datacloud.eu/deep-hdc/repos/deep-2-ubuntu16_04.list
* Ubuntu 18.04 - https://repo.indigo-datacloud.eu/deep-hdc/repos/deep-2-ubuntu18_04.list

or use the deephdc-release package to install DEEP-HDC repositories:

* CentOS7:
.. code-block:: bash

    # wget https://repo.indigo-datacloud.eu/repository/deep-hdc/production/2/centos7/x86_64/base/deephdc-release-2.0.0-1.el7.noarch.rpm
    # yum localinstall -y deephdc-release-2.0.0-1.el7.noarch.rpm

* Ubuntu 16.04:
.. code-block:: bash

    # wget https://repo.indigo-datacloud.eu/repository/deep-hdc/2/ubuntu/dists/xenial/main/binary-amd64/deephdc-release_2.0.0-1_amd64.deb
    # dpkg -i deephdc-release_2.0.0-1_amd64.deb

* Ubuntu 18.04:
.. code-block:: bash

    # wget https://repo.indigo-datacloud.eu/repository/deep-hdc/2/ubuntu/dists/bionic/main/binary-amd64/deephdc-release_2.0.0-1_amd64.deb
    # dpkg -i deephdc-release_2.0.0-1_amd64.deb

These packages will install required dependencies, the INDIGO - DataCloud
public key and ensures the precedence of DEEP-HybridDataCloud repositories
over EPEL and Ubuntu.

It is strongly recommended the use of the lastest version of the
**deephdc-release** packages containing the public key and the YUM and APT
repository files.

Enable the DEEP-HDC Containers repositories
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

On the `DockerHub Registry <https://hub.docker.com/>`__, DEEP -
HybridDataCloud uses the INDIGO - DataCloud and DEEP-HDC Organizations:

* `indigodatacloud <https://hub.docker.com/orgs/indigodatacloud/repositories>`__, for Core Services
* `deephdc <https://hub.docker.com/orgs/deephdc/repositories>`__, for DEEP-OC modules

Containers present in those repositories and released in DEEP-1 major release are
tagged with “DEEP-2” tag and signed, leveraging the `Docker’s trust
features <https://docs.docker.com/engine/security/>`_ so that users can pull trusted images.

Currently, content trust is disabled by default. You must enable it by setting
the ``DOCKER_CONTENT_TRUST`` environment variable, like below:

.. code-block:: bash

  export DOCKER_CONTENT_TRUST=1

For more details regarding the "Content Trust in Docker" please read `Docker's Documentation <https://docs.docker.com/engine/security/trust/content_trust/>`_

Content trust is associated with the TAG portion of an image.
For DEEP-2 (Rosetta) release the signed tag is DEEP-2. See example bellow
if you want to ensure the correct use of DEEP-HDC images:

.. code-block:: bash

  $ export DOCKER_CONTENT_TRUST=1

  $ docker pull indigodatacloud/orchestrator:2.2.0-FINAL
  No trust data for 2.2.0-FINAL

  $ docker pull indigodatacloud/orchestrator:DEEP-2
  Pull (1 of 1): indigodatacloud/orchestrator:DEEP-2@sha256:441c8b037684422ccdf2fdec322c9c09904ed3ce74d9fcc7d2862a9f53ad36be
  sha256:441c8b037684422ccdf2fdec322c9c09904ed3ce74d9fcc7d2862a9f53ad36be: Pulling from indigodatacloud/orchestrator
  93857f76ae30: Pull complete
  [...]
  e8c92b40b492: Pull complete
  Digest: sha256:441c8b037684422ccdf2fdec322c9c09904ed3ce74d9fcc7d2862a9f53ad36be
  Status: Downloaded newer image for indigodatacloud/orchestrator@sha256:441c8b037684422ccdf2fdec322c9c09904ed3ce74d9fcc7d2862a9f53ad36be
  Tagging indigodatacloud/orchestrator@sha256:441c8b037684422ccdf2fdec322c9c09904ed3ce74d9fcc7d2862a9f53ad36be as indigodatacloud/orchestrator:indigo_2
  $ docker images
  REPOSITORY                     TAG                 IMAGE ID            CREATED             SIZE
  indigodatacloud/orchestrator   DEEP-2            xxxxxxxxxxx        1 hours ago        843MB

Documentation
-------------

Please find DEEP-2 services and components documentation
at `Included components`_.

Support
-------

Most complex software contains bugs, we are not an exception. One of the
features of free and open source software is the ability to report bugs,
helping to fix or improve the software you use.

DEEP - HybridDataCloud project uses the `INDIGO Catch-All GGUS - Support Unit <https://wiki.egi.eu/wiki/GGUS:INDIGO_DataCloud_Catch-all_FAQ>`_ and
the *deep-support@listas.csic.eu* for general support requests.
More details regarding each product support channels are provided in the
respective products release pages.

Developers, researchers and IT enthusiasts: feel free to write to
*deep-info@listas.csic.es* to ask for more information on how to use DEEP solutions
for your work. For automatic notifications you can register to the DEEP
- HybridDataCloud release RSS feed or subscribe to the DEEP -
HybridDataCloud Announce Mailing list. You can also socialize with us
via `Twitter <http://twitter.com/DEEP_eu>`_ or by joining our `LinkedIn group <https://www.linkedin.com/groups/12093546>`_.

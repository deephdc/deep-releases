Welcome to DEEP-Hybrid-DataCloud releases's page
================================================

You'll find here usefull information regarding the DEEP-HybridDataCloud
services and components **releases**, their schedules, documentation and
support.

DEEP-Hybrid-DataCloud releases
------------------------------

.. toctree::
   :maxdepth: 2

   releases/genesis/index.rst


Release repositories
--------------------

DEEP-HDC **production** (stable) repositories: 

* `deep-hdc/production/{1,2}/centos7/x86_64/{base|updates} <http://repo.indigo-datacloud.eu/repository/deep-hdc/production/1/centos7/x86_64/base/repoview/>`_
* `deep-hdc/production/{1,2}/ubuntu/dists/xenial/main/{binary-amd64,source} <http://repo.indigo-datacloud.eu/repository/deep-hdc/production/1/ubuntu/dists/xenial/main/>`_

  * containing signed, well tested software components

* third-party:

  * `deep-hdc/production/{1,2}/centos7/x86_64/third-party <http://repo.indigo-datacloud.eu/repository/deep-hdc/production/1/centos7/x86_64/third-party/repoview>`_
  * `deep-hdc/production/{1,2}/ubuntu/dists/xenial/third-party{binary-amd64,source} <http://repo.indigo-datacloud.eu/repository/deep-hdc/production/1/ubuntu/dists/xenial/third-party>`_

    * containing packages that are not part of DEEP-HDC project, or not part of the base OS or EPEL, but used as dependencies by other DEEP-HDC components

YUM & APT **configuration files** are available `here <http://repo.indigo-datacloud.eu/deep-hdc/repos>`_
or use the **deephdc-release** package to install DEEP-HDC repositories

Release schedule
----------------

* Time-based releases
   - **projects’ Major releases** - the DEEP-HybridDataCloud project foresees two major releases, distributions, during its lifetime, at around 10 months since the start of the project.
* As-soon-as-available
   - **components’ Minor/Revision releases** - in a project Major release, Development teams (aka Product Teams) can release updated versions of their components as soon as the DEEP-HDC software quality criteria are met. Thought the project Continuous Integration and Delivery System tests are continuously run giving feedback on the status of the components.

Support Model
~~~~~~~~~~~~~

-  in a Major Release for each component or service only the latest
   revision released is supported.
-  for each component or service a (major) release is supported at least
   for the lifetime of the projects’ major release in which this version
   was released the first time.

Supported platforms
-------------------

*  DEEP-HybridDataCloud releases are supported for the following
   platforms:

   * CentOS7 & Ubuntu 16.04
      * for the products distributed through rpms and deb packages
   * all platforms supporting Docker continers
      * for the products distributed as docker images 

Supported artifacts & packaging formats
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

-  Packages:

   -  Binaries: executable packages
   -  Sources: when available, package files that contain all of the necessary files to compile/build the respective piece of software
   -  Tarballs: clients are distributed as tarballs for all the platforms

- Containers: Docker images are available for almost all project software


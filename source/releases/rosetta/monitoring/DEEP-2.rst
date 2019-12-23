v DEEP-2
------

What’s new
~~~~~~~~~~

This is the first release of Monitoring framework through the DEEP-HDC project, providing new 
verion of Openstack, Mesos and QCG probes:

* `Openstack zabbix probe v. 1.4 <https://jira.deep-hybrid-datacloud.eu/projects/DPD/versions/10801>`_
* `Mesos probe v. 1.4 <https://jira.deep-hybrid-datacloud.eu/projects/DPD/versions/10802>`_
* `QCG probe v. 1.4 <https://jira.deep-hybrid-datacloud.eu/projects/DPD/versions/10803>`_

Some of the main new common new features are:
* Integration with the Orchestrator services and providers convention
* Integration with DEEP IAM
* Integration with DEEP CMDB

List of RfCs
~~~~~~~~~~~~

 .. raw:: html

    <embed>
    <h3> Openstack probe
    </h3>
    <h4>        Bugs
    </h4>
    <ul>
    <li>[<a href='https://jira.deep-hybrid-datacloud.eu/browse/DPD-578'>DPD-578</a>] -         No support for Glance API v2
    </li>
    <li>[<a href='https://jira.deep-hybrid-datacloud.eu/browse/DPD-646'>DPD-646</a>] -         Openstack Probe result log message
    </li>
    <li>[<a href='https://jira.deep-hybrid-datacloud.eu/browse/DPD-647'>DPD-647</a>] -         Openstack probe metrics sent to Zabbix
    </li>
    <li>[<a href='https://jira.deep-hybrid-datacloud.eu/browse/DPD-648'>DPD-648</a>] -         Openstack probe failure at IFCA site
    </li>
    <li>[<a href='https://jira.deep-hybrid-datacloud.eu/browse/DPD-662'>DPD-662</a>] -         Change service_type for nova
    </li>
    <li>[<a href='https://jira.deep-hybrid-datacloud.eu/browse/DPD-677'>DPD-677</a>] -         Openstack probe: missing bash script &amp; log properties
    </li>
    </ul>

    <h3> Generic & Common Bugs
    </h3>
    <ul>
    <li>[<a href='https://github.com/indigo-dc/Monitoring/issues/83'>Issue-83</a>] - MesosZabbixProbe RPM does not work on CentOS 7.5 
    <li>[<a href='https://github.com/indigo-dc/Monitoring/issues/81'>Issue-81</a>] - Document the use of the tag "providers.exceptions" 
    <li>[<a href='https://github.com/indigo-dc/Monitoring/issues/10'>Issue-10</a>] - Connection to the Zabbix Wrapper fails 
    <li>[<a href='https://github.com/indigo-dc/Monitoring/issues/6'>Issue-6</a>] - No error control when not finding the config file 
    </li>
    </ul>  


    </embed>

## Mesos probe
* Updated to version 1.4
* CMDB integration now is mandatory, so ```cmdb.location``` property now is mandatory in the configuration
* Updated to provide new convention of groups and hosts (read below)

## Groups and hosts semantics
This release changes the semantics of groups and hosts when sending metrics to the Zabbix server:

* Since CMDB integration is now mandatory for both probes, provider name will be used as group 
name when sending metrics to the server
* Host name will be the service ID

So for example, if we have two providers with the following services:

- IFCA
  - "s1": Mesos
  - "s2": OpenStack1
  - "s3": OpenStack2
- INFN
  - "s1": OpenStack

In this case, this means that the provider IFCA has one Mesos cluster and two OpenStack instances
 running while the provider INFN has just one OpenStack installation.

 In this scenario the OpenStack probe will create two groups (if they don't exist) 
 named ```IFCA``` and ```INFN``` and it will register metrics under the host 
 name ```s2``` and ```s3``` for group ```IFCA``` and ```s1``` for group ```INFN```, meaning 
 that metrics under the host ```s2``` and group ```IFCA``` will be the ones related to 
 the ```OpenStack1``` instance running at ```IFCA``` provider. The same applies to 
 the ```OpenStack2``` instance in ```IFCA``` and the only OpenStack instance at ```INFN``` (in 
 this case, the group would be ```INFN``` instead of ```IFCA```).

The Mesos probe will do the same but given that there's only one Mesos cluster in IFCA it will 
create (if it doesn't exist) a group ```IFCA``` and a host with name ```s1``` to send its metrics.

Installation methods
~~~~~~~~~~~~~~~~~~~~

* Mesos: https://github.com/indigo-dc/Monitoring/blob/master/doc/mesos.md#3-installation
* Openstack: https://github.com/indigo-dc/Monitoring/blob/master/doc/OPENSTACK.md#3-installation
* QCG: https://github.com/indigo-dc/Monitoring/blob/master/doc/QCG.md#3-installation


List of Artifacts
~~~~~~~~~~~~~~~~~


* CentOS-7 RPMS
    * Openstack probe `openstack-zabbix-probe-1.4.2-2.noarch.rpm <http://repo.indigo-datacloud.eu/repository/deep-hdc/production/2/centos7/x86_64/base/repoview/openstack-zabbix-probe.html>`_
    * Mesos probe `MesosZabbixProbe-1.4-1.noarch.rpm <http://repo.indigo-datacloud.eu/repository/deep-hdc/production/2/centos7/x86_64/base/repoview/MesosZabbixProbe.html>`_
    * QCG probe `QCGZabbixProbe-1.0-1.noarch.rpm <http://repo.indigo-datacloud.eu/repository/deep-hdc/production/2/centos7/x86_64/base/repoview/QCGZabbixProbe-1.0-1.html>`_

* Ubuntu 16.04 DEBS
    * Openstack probe `openstack-zabbix-probe-1.4.2_all.deb <http://repo.indigo-datacloud.eu/repository/deep-hdc/production/2/ubuntu/dists/xenial/main/binary-amd64/openstack-zabbix-probe-1.4.2_all.deb>`_
    * Mesos probe `mesos-zabbix-probe_1.4_all.deb <http://repo.indigo-datacloud.eu/repository/deep-hdc/production/2/ubuntu/dists/xenial/main/binary-amd64/mesos-zabbix-probe_1.4_all.deb>`_
    * QCG probe `qcg-zabbix-probe-1.0_all.deb <http://repo.indigo-datacloud.eu/repository/deep-hdc/production/2/ubuntu/dists/xenial/main/binary-amd64/qcg-zabbix-probe-1.0_all.deb>`_

* Ubuntu 18.04 DEBS
    * Openstack probe `openstack-zabbix-probe-1.4.2_all.deb <http://repo.indigo-datacloud.eu/repository/deep-hdc/production/2/ubuntu/dists/bionic/main/binary-amd64/openstack-zabbix-probe-1.4.2_all.deb>`_
    * Mesos probe `mesos-zabbix-probe_1.4_all.deb <http://repo.indigo-datacloud.eu/repository/deep-hdc/production/2/ubuntu/dists/bionic/main/binary-amd64/mesos-zabbix-probe_1.4_all.deb>`_
    * QCG probe `qcg-zabbix-probe-1.0_all.deb <http://repo.indigo-datacloud.eu/repository/deep-hdc/production/2/ubuntu/dists/bionic/main/binary-amd64/qcg-zabbix-probe-1.0_all.deb>`_

 

Alien4Cloud - DEEP plugin
=========================

.. contents:: Table of Contents

Cloud computing has been established in recent years as the key
technology to offer on-demand access to computing and storage resources.
This has been exemplified by both public Cloud providers and on-premises
Cloud Management Platforms such as OpenNebula and OpenStack, out of
which federated large-scale Cloud infrastructures to support scientific
computing have been established, such as the EGI Federated Cloud.
Indeed, the European Open Science Cloud (EOSC) is foreseen to consist of
a federating core which provides seamless access to a wide range of
publicly funded services supplied at national, regional, and
institutional levels for science and innovation. These last years have
witnessed the rise of the OASIS TOSCA (Topology Orchestration for the
Specification of Cloud Applications) standard, adopted by several
European projects. This standard allows one to specify the components
that underpin an application architecture using a high-level YAML-based
language which can be extended to include additional components to
satisfy the requirements of a wide variety of applications. However, the
recent advances in computing have revealed two major trends that can
greatly benefit the application delivery and the computational
performance: Linux containers and GPU computing. To this aim, the
Horizon 2020 DEEP-Hybrid DataCloud project is developing innovative
services to facilitate the composition and deployment of complex cloud
application architectures across multiple Clouds (both private and
public ones).

The **Alien4Cloud - DEEP plugin** is the first step towards the adoption
of a visual composition approach of TOSCA templates (based on
Alien4Cloud), in order to facilitate the widespread adoption of the
standard, and its integration with the INDIGO-DataCloud Orchestrator,
which is already part of the EOSC-HUB service catalogue. \* With this
approach, the user can visually compose complex applications that
involve, for example, the dynamic deployment of a container
orchestration platform on an IaaS Cloud site that executes a
highly-available Docker-based application to facilitate application
delivery. \* The users can also deploy an Apache Mesos cluster with GPU
support that contains a deep learning application for the recognition of
certain plant species, offered as a service to a community of users.
This introduces unprecedented flexibility, from visual composition, to
the automated application delivery, using a graphical interface that is
already integrated with an Orchestrator layer that performs resource
provision from multiple Clouds and application configuration. \* The
integration of easy-to-use graphical interfaces builds a bridge between
the users and the orchestration services.It also represents a step
forward to foster the adoption of innovative computing services that are
hidden from the user, as they can focus on the high-level description of
the services requirements and definition, instead of working on their
technical implementation.

Release Notes
-------------

.. toctree::
   :maxdepth: 1
   :glob:

   a4c-deep/*

Documentation
-------------

Detaield documentation is available at:
https://github.com/indigo-dc/alien4cloud-deep/blob/master/README.md

Support
-------

GitHub issues: https://github.com/indigo-dc/alien4cloud-deep/issues DEEP
project’s internal support ticketing system:
http://jira.deep-hybrid-datacloud.eu/

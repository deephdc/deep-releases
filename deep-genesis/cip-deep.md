---
layout: default
title: CloudInfoProvider-DEEP
New field 1: Alien4Cloud - DEEP plugin
---

# CloudInfoProvider-DEEP v. 0.10.4
**Description of CIP-DEEP
**

Summary:

* [Release Notes](#rn)
	* [What's new](#wn)
	* [List of RfCs](#lrfc)
	* [Known Issues](#kn)
	* [List of Artifacts](#la)
* [Documentation](#doc)
* [Support](#su)

<a name="rn">&nbsp;</a>
## Release Notes

<a name="wn">&nbsp;</a>
### What's new
This versions adds InfiniBand support for OpenStack in LDIF format:
* cloud-info-provider shall provides now information, through GLUE2ResourceID, when a given OpenStack flavor provides InfiniBand.
	* The convention is to use the extra_specs parameter from the flavor's metadata. This parameter is a list of key:value pairs, where the both key's and value's names are not fixed. The provider should allow to define the key's name and the value string to match via command-line options. The InfiniBand support will be published through the GLUE2ExecutionEnvironmentNetworkInfo attribute.


<a name="lrfc">&nbsp;</a>
### List of RfCs

* Add InfiniBand support for OpenStack in LDIF format

<a name="kn">&nbsp;</a>
### Known Issues

<a name="la">&nbsp;</a>
### List of Artifacts

<a name="doc">&nbsp;</a>
### Documentation

<a name="su">&nbsp;</a>
### Support

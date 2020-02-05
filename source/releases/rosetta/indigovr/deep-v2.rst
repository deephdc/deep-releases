DEEP-v2
------

What’s new
~~~~~~~~~~

* support for OpenStack
* added parameter for MTU size - to prevent hanging out connections in case of MTU problems
* added option for private subnet
* use-case for elastic clusters - certificate for machine with re-used hostname
* various other fixes (CentOS, internal certificates)

List of RfCs
~~~~~~~~~~~~

  .. raw:: html

    <embed>
    <h4> GitHub Issues: improvements and bug fixes
    </h4>
    <ul>
    <li>[<a href='https://github.com/indigo-dc/ansible-role-indigovr/issues/15'>Issue 5</a>] - Error generating standalone certificates of different nodes with same name 
    </li>
    <li>[<a href='https://github.com/indigo-dc/ansible-role-indigovr/pull/10'>Pull-10</a>] - Fixes from testing in OpenStack
    </li>
    <li>[<a href='https://github.com/indigo-dc/ansible-role-indigovr/pull/11'>Pull-11</a>] - Fix errors with dirs
    </li>
    <li>[<a href='https://github.com/indigo-dc/ansible-role-indigovr/pull/12'>Pull-12</a>] - Add start task 
    </li>
    <li>[<a href='https://github.com/indigo-dc/ansible-role-indigovr/pull/13'>Pull-13</a>] - Fix vpn prefix in route-gateway 
    </li>
    <li>[<a href='https://github.com/indigo-dc/ansible-role-indigovr/pull/14'>Pull-14</a>] - Adding MTU parameter for fragment and mssfix, default empty
    </li>
    <li>[<a href='https://github.com/indigo-dc/ansible-role-indigovr/pull/16'>Pull-16</a>] -  Add stat to check if certificate exists
    </li>
    <li>[<a href='https://github.com/indigo-dc/ansible-role-indigovr/pull/17'>Pull-17</a>] - Re-use recipes for certificate signing in vrouter and standalone
    </li>    
    </ul>
 
    <br>
    </embed>

Known Issues
~~~~~~~~~~~~

* None

Installation methods
~~~~~~~~~~~~~~~~~~~~

* Automatic deployment - ansible module used by Infrastructure Manager.

  * Project URL: https://github.com/indigo-dc/ansible-role-indigovr

List of Artifacts
~~~~~~~~~~~~~~~~~

* Ansible Roles
    * https://galaxy.ansible.com/indigo-dc/indigovr


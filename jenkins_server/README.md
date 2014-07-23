Jenkins Server
==============

Provisioning for a Jenkins CI server for Plone projects.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

  * jenkins_port: The port Jenkins listens on (default: 8080).

  * jenkins_url: The URL Jenkins uses.

  * jenkins_plugins: A list of Jenkins plugins that will be installed.

  * jenkins_nodes: List of nodes that Jenkins server connects to.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

- plone.jenkins_node (tbc)


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: jenkins.plone.org
      roles:
         - { role: username.rolename, x: 42 }

License
-------

GPLv2

Author Information
------------------

Plone Community.

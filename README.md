Jenkins Server
==============

Provisioning for a [Jenkins CI server](http://jenkins-ci.org/) with [Nginx](http://nginx.org/) for [Plone](https://plone.org/) projects.

Requirements
------------

None.

Role Variables
--------------

You can set different variables, to do that change the ones in *defaults/main.yml* or even better add them to *vars/main.yml*.

  * jenkins_port: The port Jenkins listens on (default: 8080).

  * jenkins_url: The URL Jenkins uses.

  * jenkins_plugins: A list of Jenkins plugins that will be installed.



Dependencies
------------

- plone.jenkins_node (tbc)


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: jenkins.plone.org
      roles:
         - { role: plone.jenkins_server }

License
-------

GPLv2

Author Information
------------------

Plone Community.

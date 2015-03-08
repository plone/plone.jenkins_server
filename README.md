Jenkins Server
==============

Provisioning for a [Jenkins CI server](http://jenkins-ci.org/) with [Nginx](http://nginx.org/) for [Plone](https://plone.org/) projects.

Requirements
------------

None.

Role Variables
--------------

You can set different variables,
that change the ones in *defaults/main.yml* or even better add them to *vars/main.yml*.

  * jenkins_port: The port Jenkins listens on (default: 8080).

  * jenkins_url: The URL Jenkins uses.


Example Playbook
----------------

Example of how to use this role:

    - hosts: jenkins.plone.org
      roles:
        - plone.jenkins_server
      vars:
        admin_email: my@email.org
        simple_theme_css_url: https://rawgit.com/plone/jenkins.plone.org/master/jenkins.plone.org.css
        simple_theme_js_url: https://cdnjs.cloudflare.com/ajax/libs/doony/2.1/js/doony.min.js
        jenkins_admins:
          - tisto
          - gforcada
        github_orgs:
          - plone
          - collective
        node_names:
          - node1
          - node2
        github_app_client_id: 1234567890
        github_app_client_secret: 1234567890abcdef1234567890abcdef1234567890abcdef

Nodes playbook
--------------

Looking for the ansible playbook for nodes?
Look no further: [plone.jenkins_node](https://github.com/plone/plone.jenkins_node/)

License
-------

GPLv2

Author Information
------------------

Plone Community.

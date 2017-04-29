Jenkins server
==============
Provisioning for a [Jenkins CI server](http://jenkins-ci.org/) with [Nginx](http://nginx.org/) for [Plone](https://plone.org/) projects.

Requirements
------------
None.

Role variables
--------------
You can set different variables,
that change the ones in *defaults/main.yml* or even better add them to *vars/main.yml*.

  * jenkins_url: The URL Jenkins uses (default: ``http://jenkins.plone.org``)
  * jenkins_server_name: The FQDN (default: ``jenkins.plone.org``)
  * jenkins_port: The port Jenkins listens on (default: ``8080``)
  * roboto_port: The port mr.roboto will be used *(needs to be made conditional)*
  * dependencies: System level dependencies (default: ``nginx``)

For a successful provisioning,
this role needs some other variables, that **must** be provided:

  * github_app_client_id: For GitHub Oauth integration *(needs to be made conditional)*
  * github_app_client_secret: For GitHub Oauth integration *(needs to be made conditional)*
  * jenkins_admins: GitHub user ids that will be admins, used by GitHub Oauth *(needs to be made conditional)*
  * github_orgs: GitHub organizations covered, used by GitHub Oauth *(needs to be made conditional)*
  * nodes_info: list of dictionaries with information regarding a node (name, host and IP)
  * admin_email: That's it, your email
  * simple_theme_css_url: URL to a CSS file for UI customizations *(needs to be made conditional)*
  * simple_theme_js_url: URL to a JS file for UI/interaction customizations *(needs to be made conditional)*

Example playbook
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
        nodes_info:
          - name: "Node1"
            host: "node1.jenkins.plone.org"
            port: "8081"
          - name: "Node2"
            host: "node2.jenkins.plone.org"
            port: "8082"
        github_app_client_id: 1234567890
        github_app_client_secret: 1234567890abcdef1234567890abcdef1234567890abcdef

Nodes playbook
--------------
Looking for the ansible playbook for nodes?

Look no further: [plone.jenkins_node](https://galaxy.ansible.com/list#/roles/3517)

License
-------
GPLv2

Author information
------------------
[Plone](https://plone.org/) Community.

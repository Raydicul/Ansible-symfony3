# Provision Debian 8 - Deploy Symfony3 app


## Description

The provision.yml script will install :
  - php 5.6
  - apache2
  - mysql
  - git
  
The deploy.yml script will deploy a symfony3 application to /var/www from a git repository


## Installation

Install ansible-galaxy requirements
```
$ ansible-galaxy install -r requirements.yml
```
### Server provision

Edit :
  - hosts file to define server connection
  - /vars/provision.yml (/vars/provision_dev.yml)
  - provision.yml to specify the vars/ file to use

Run provision script
```
$ ansible-playbook -i hosts provision.yml
```

### Symfony3 deployment

Edit :
  - hosts file to define server connection
  - /vars/deploy.yml

Run deploy script
```
$ ansible-playbook -i hosts deploy.yml
```

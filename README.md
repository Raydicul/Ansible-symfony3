# Provision Debian 8 - Deploy Symfony3
---

## Description

The provision.yml script will install :
  - php 5.6
  - apache2
  - mysql
  - git
  
The deploy.yml script will deploy a symfony 3 application to /var/www from a git repository


## Installation

Install ansible-galaxy requirements
```
$ ansible-galaxy install -r requirements.yml
```

Edit :
  - hosts file to define the 


Run provision script
```
$ ansible-playbook -i hosts provision.yml
```

Run deploy script
```
$ ansible-playbook -i hosts deploy.yml
```


File to edit : 
  - hosts
  - var/provision
  - var/deploy

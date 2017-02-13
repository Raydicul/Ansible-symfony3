# Provision Debian 8 - Deploy Symfony3 app


The `provision.yml` script will install :
  - php 7.0
  - apache2
  - mysql
  - git
  
  
The `deploy.yml` script will deploy a symfony3 application to `/var/www` from a git repository in a Capifony style

## Requirements


  - Ssh access to a server with Debian 8 Jessie
  - Ansible

## Installation


Install ansible-galaxy requirements
```
$ ansible-galaxy install -r requirements.yml
```


### Server provision


Update Debian : https://www.cyberciti.biz/faq/installing-php-7-on-debian-linux-8-jessie-wheezy-using-apt-get/

```
$ sudo -s
$ echo 'deb http://packages.dotdeb.org jessie all' >> /etc/apt/sources.list
$ echo 'deb-src http://packages.dotdeb.org jessie all' >> /etc/apt/sources.list

$ cd /tmp
$ wget https://www.dotdeb.org/dotdeb.gpg
$ sudo apt-key add dotdeb.gpg
$ rm dotdeb.gpg
```

Edit :
  - `hosts` file to define server connection
  - `/vars/provision.yml` (`/vars/provision_dev.yml` for dev)
  - `provision.yml` to specify the `vars/` file to use

Run provision script
```
$ ansible-playbook -i hosts provision.yml
```


### Symfony3 deployment


Edit :
  - `hosts` file to define server connection
  - `/vars/deploy.yml`

Run deploy script
```
$ ansible-playbook -i hosts deploy.yml
```

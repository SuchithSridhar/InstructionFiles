## Set up ssh

Add the ssh keys to the machine easy ssh login:

> ssh-copy-id -i ~/.ssh/id_rsa.pub root@suchicodes.info

## Installation

> apt update && apt upgrade
> apt install nginx python-certbot-nginx nodejs python-pip

## Add Users

> useradd -m -G sudo -s /bin/bash moni
> passwd moni

#### Make a common user

> useradd -m commonUser

Add the current users to the user group

> usermod -aG moni commonUser

Allow read-write access to commonUser folders

> chmod -R 664 /home/commonUser
> find /home/commonUser -type d -exec chmod 775 {} \;

#### Linking from commonUser to users

Example bootstrap5 folder in commonUser home dir.

> ln -s <target> <src>

> ln -s /home/commonUser/bootstrap5 /home/moni/website

Rename your link to the file:

> mv /home/moni/website/bootstrap5 /home/moni/website/bootstrap

### Writing nginx config

Write the nginx config files in home dir and link to sites-available
and then sites-enables to activate the website.

###

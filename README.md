# Docker lnmp

This is a PHP runtime environment which base on docker.

The services provided include but not limited to **nginx** **php** and **mysql**.

In future functions, plan to join _mongdb_ _redis_ and _ELK_ equal services.

You can run this software on linux or windows or mac, recommending use of x86_64 linux platforms.

If you run on a mac, please reference https://docs.docker.com/docker-for-mac/osxfs/#namespaces share you mount directory.

 really want your feedback when you have Iproblems encountered during use.

## Dependencies

git version 1.8.3.1 or higher

docker version 17.09.0-ce or higher

docker-compose version 1.16.1 or higher

## Get installed
    
    $ git clone https://github.com/yinfuyuan/docker-lnmp.git

## Get started

    $ docker-compose up -d
    
    # echo '127.0.0.1 www.example.com' >> /etc/hosts
    
    $ curl -i -X HEAD www.example.com

## Configure

### nginx
    
The nginx config file at the directory /services/nginx/config/
You don't have to modify nginx.con, if you want to add some domains.
You can copy /services/nginx/config/conf.d/example.conf to a new file.
Change this file and exec the following commands to make it effective.

    # docker-compose restart nginx 
    
### others

By default, the services config file are both at /services/[service]/config/ directory.
You can modify the config files accordingly to your needs.

## Features

* All configuration files are mounted outside the container.

## Recommending usage

* All the /volumes/ files both should be soft links to external files.
* /volumes/application/http use domain name upside down tree.


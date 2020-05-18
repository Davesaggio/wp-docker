# WP-DOCKER

## Project setup

You first need to add a custom host for you website in the `hosts` file, if you use macOS run the following command to edit it:
```
sudo vim /private/etc/hosts
```
and add this line `127.0.0.1 my-website-name.local`.

You also need to edit the `VIRTUAL_HOST` key contained in the `docker-compose.yml` which is placed in the root of this project, in our case it will be:
`VIRTUAL_HOST: my-website-name.local 127.0.0.1 my-website-name.local`

`docker-compose.yml` file contains all the configuration for your wordpress website and its database, feel free to edit or make any changes you deem necessary.

## Installation

From the root of this project:
```
cd proxy
docker network create proxy
docker-compose up -d
cd ..
docker-compose up -d
mv phpmyadmin.php ./public
```

Proxy and your wordpress website containers are now created, make sure they are both up, if everything went well you are ready to go!

Your website is available at `my-website-name.local`, you can also access your db at `my-website-name.local/phpmyadmin.php`



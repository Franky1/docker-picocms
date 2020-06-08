# PicoCMS Docker Container

This is a dockerized version of **PicoCMS**, a flat file content management system using Markdown, developed at <http://picocms.org>

## Issues

> **_W.I.P._** <br>
> Dont use this repo, it doesn't work anymore... <br>
> _Installation changed - does not apply anymore to Pico 2.x_ <br>
> _Needs to be fixed..._ <br>
> Last Changes: 08.06.2020

### Installation Tutorials

- <http://picocms.org/docs/>
- <https://www.howtoforge.com/how-to-install-pico-cms-on-debian-10/>
- <https://websiteforstudents.com/install-pico-cms-on-ubuntu-16-04-18-04-18-10-with-apache2-and-php-7-2/>
- <https://www.linuxcloudvps.com/blog/install-and-configure-pico-cms-on-ubuntu-16-04/>
- <https://github.com/shevabam/dockerfiles/tree/master/pico-cms>
- <https://github.com/t-matsuo/docker-pico>

## Setup Options

1. Linux machine with `docker` and `docker-compose` installed.
2. Linux machine run with **VirtualBox** and **Vagrant**.

### Setup Option 1 (Linux Machine)

#### Pre-requisites

- Install **Docker** and **Docker Compose**
- Git clone this project

#### Usage

Use the standard `docker-compose` commands:

1. `docker-compose build` to build the image(s)
2. `docker-compose up -d` to run the container(s)
3. `docker-compose stop` to stop the container(s)
4. `docker-compose down` to remove the container(s)
5. `docker-compose down --volumes` to remove the container(s) and all associated volumes

### Setup Option 2 (Vagrant)

#### Pre-requisites (Vagrant)

- Install **VirtualBox** and **Vagrant**
- Git clone this project

#### Usage (Vagrant)

1. `vagrant up` to pull box, run and provision
2. `vagrant ssh` into the machine
3. `sudo docker-compose up -d` to to run the container

tbd. Not finished yet here...

Visit: <http://10.0.23.19>

## PicoCMS volumes

Once up and running, 4 docker volumes allow changes directly into the container:

- **plugins**: [pico_edit](https://github.com/blocknotes/pico_edit) plugin is pre-installed. Follow PicoCMS doc to [install plugins](http://picocms.org/docs/#plugins).  ([Find more plugins](https://github.com/picocms/Pico/wiki/Pico-Plugins))
- **themes**: the default theme is installed. Follow PicoCMS doc to [add or edit themes](http://picocms.org/docs/#themes). ([Find more themes](http://picocms.org/themes/))
- **content**: the initial sample content files are present. Follow PicoCMS doc to [create content](http://picocms.org/docs/#creating-content)
- **config**: The default config is set up. Follow PicoCMS doc to [change configuration](http://picocms.org/docs/#config)

## PicoCMS Backend - Pico Edit

The **pico_edit** plugin is pre-installed ([https://github.com/blocknotes/pico_edit](https://github.com/blocknotes/pico_edit)),. It enables editing pages directly from the web browser via a password-protected interface.

### Access the backend

- Visit: <http://your_site/pico_edit>
- Visit: <http://10.0.23.19/pico_edit>
- Initial password: `password`

### Change the backend password

1. Generate SHA-1 from your desired password at [http://www.sha1-online.com/](http://www.sha1-online.com/)
2. Edit the file `plugins/pico_cms/config.php` and insert your sha1 hashed password instead of the existing one (variable *$backend_password*).

## Keeping the system up-to-date

- Check Box Version `config.vm.box` in `Vagrantfile` for newer versions
- Check Base Image `FROM` in `Dockerfile` for newer versions
- Check `s6-overlay` Download URL in `Dockerfile` for newer versions
- Check for errors during build or run process

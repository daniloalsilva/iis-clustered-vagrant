# IIS Web Server clustered

----


## Pre-requisites:
- Virtualbox
- Vagrant
  - Vagrant boxes "davydany/Windows2016" and "ubuntu/trusty64" (downloaded during project execution)

## How to execute this project:

- In a terminal/console, into your projects folder, clone this repository:
```
git clone https://github.com/daniloalsilva/iis-clustered-vagrant.git
```
- Change the current dir in terminal/console and execute vagrant:
```
cd iis-clustered-vagrant
vagrant up
```
- If you want to shutdown or destroy the created environment, just run `vagrant halt` or `vagrant destroy` respectively.
# IIS Web Server clustered

## Description

This project uses **vagrant** and **virtualbox** to create 2 virtual machines running **windows 2016** (web servers) and 1 virtual machine running **Ubuntu** (load balancer).

## Pre-requisites:
- Virtualbox
- Vagrant
  - Vagrant boxes *"davydany/Windows2016"* and *"ubuntu/trusty64"* (downloaded during project execution)

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
- You can access the website locally, using the address http://192.168.33.12 (lb ip), which will show the contents of iis web servers, using round robin load balancing distribution.
- If you want to shutdown or destroy the created environment, just run `vagrant halt` or `vagrant destroy` respectively.
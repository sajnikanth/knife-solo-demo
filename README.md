Objective / Background
======================

Provision a remote server using knife solo; cookbooks managed by berkshelf

Pre-Requisites
==============

* You already understand what's happening here - https://github.com/sajnikanth/berksdemo
* A Vagrant VM up and running using the Vagrantfile in this repo
* An EC2 instance (open ports 22 and 80) up and running. Update `~/.ssh/config` so you can ssh into it like so `ssh ec2`.

Run
===

* `git clone git@github.com:sajnikanth/knife-solo-demo.git && cd knife-solo-demo`
* `bundle install` - install all pre-requisite gems - chef, knife-solo, berkshelf
* `berks install --path cookbooks/` #cookbooks get downloaded to cookbooks folder
* `knife solo prepare vagrant@192.168.12.34` - installs chef solo on Vagrant VM
* `knife solo cook vagrant@192.168.12.34` copies cookbooks and runs the recipies on VM
* Open the browser on your host (osx) and hit 192.168.12.34; You should see a 404 from nginx (this means it is installed)
* Now we do the same for ec2, but use `knife solo bootstrap` which combines `prepare` and `cook`
* `knife solo bootstrap ec2`
* Open the browser on your host (osx) and hit ec2 machine's IP; You should see a 404 from nginx (this means it is installed)

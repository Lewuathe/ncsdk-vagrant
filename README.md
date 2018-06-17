ncsdk-vagrant
===

ncsdk-vagrant launches a Vagrant virtual machine to run an application on [Movidius neural compute stick](https://developer.movidius.com/). Currently [NCSDK](https://github.com/movidius/ncsdk) supports only Linux platform. ncsdk-vagrant enables us to run Movidius application even on macOS. 

# Prerequisites

* Vagrant: 2.1.1~
* VirtualBox: 5.2.12~
* VirtualBox Extension Pack (necessary for USB 3.0 controller)
* macOS: High Sierra 10.13.4~

# How to install

Update a NCSDK provided first.

```
$ git submodule update
``` 

NCSDK should be mounted to `/home/vagrant/ncsdk` after launching the virtual machine. 

```
$ vagrant up
$ vagrant ssh

# In virtual machine
$ cd ncsdk && make install
```

Then you can write your own application as you like. Let's check neural compute stick is properly recognized by guest machine.

```
$ cd ncsdk/examples/apps/hello_ncs_cpp
$ make 
$ ./cpp/hello_ncs_cpp
Hello NCS! Device opened normally.
Goodbye NCS!  Device Closed normally.
NCS device working.
``` 

It works!

# Reference

* [Movidius Developer Site](https://developer.movidius.com/)
* [Install VirtualBox](https://www.virtualbox.org/wiki/Downloads)



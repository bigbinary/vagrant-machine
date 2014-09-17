
## Table of Contents

* [Dependencies](#dependencies)
* [Host vs Guest](#host-machine-vs-guest-machine)
* [Setting up machine using vagrant](#setting-up-the-guest-machine-using-vagrant)
* [Verify postgres is working](#verify-that-postgresql-is-working)
* [Installations](#installations-on-the-guest-machine)

## Dependencies

You'll need to have the following tools installed for this to work

* [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
* [Vagrant](http://www.vagrantup.com/downloads.html)
* [Ansible](http://docs.ansible.com/intro_installation.html)

## host machine vs guest machine

In this README "host machine" will be used to refer to the native
machine on which vagrant is installed. Once you ssh into the vagrant
machine then that machine will be referred to as "guest machine".

## Setting up the guest machine using vagrant

```
git clone https://github.com/bigbinary/vagrant-machine.git
cd vagrant-machine
vagrant up
vagrant ssh
```

## Verify that PostgreSQL is working

To test if postgresql is properly working execute following commands in the guest machine.

Note that password is blank for user postgres.

```
psql -h localhost -U postgres --password
enter password:
SELECT table_name FROM information_schema.tables WHERE table_schema='public';
```

You should see result with zero row. It means postgres is wroking fine. Now to exit out of `psql` type `\q` and hit enter.

```
postgres=# \q
```


## Installations on the guest machine

* rvm
* PostgreSQL
* imagemagick
* phantomjs
* nodejs
* curl
* git
* ack
* tree
* custom command prompt


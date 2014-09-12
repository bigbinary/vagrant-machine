## Dependencies

You'll need to have the following tools installed for this to work

* [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
* [Vagrant](http://www.vagrantup.com/downloads.html)

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

## Installations on the guest machine

* rvm
* PostgreSQL
* curl
* git
* custom command prompt

and some more. Complete list is [here]() .


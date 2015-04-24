## Introduction

vagrant-machine builds an environment in your machine where you can install Ruby on Rails application without making any changes to your machine.

### Host machine vs Guest machine

In this README "host machine" will be used to refer to the native
machine on which vagrant is installed. Once you ssh into the vagrant
machine then that machine will be referred to as "guest machine"

## Using vagrant-machine

* 1. [Dependencies](#dependencies)
* [Host vs Guest](#host-machine-vs-guest-machine)
* [Setting up machine using vagrant](#setting-up-the-guest-machine-using-vagrant)
* [Verify postgres is working](#verify-that-postgresql-is-working)
* [Installations](#installations-on-the-guest-machine)

### Dependencies

Please install following tools

* [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
* [Vagrant](http://www.vagrantup.com/downloads.html)
* [Ansible](http://docs.ansible.com/intro_installation.html)

.

#### Setting up the guest machine using vagrant

```
git clone https://github.com/bigbinary/vagrant-machine.git
cd vagrant-machine
```

Open `provisioning/group_vars/all` and change the "name" and "email" value to
have your name and your email address.

Open `provisioning/ruby/tasks/main.yml` and change the ruby verion. If
you need more than one ruby version then add another row.

Now execute following commands.

```
vagrant up
vagrant ssh
```

### Verify that PostgreSQL is working

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

### Installations on the guest machine

* [rvm](http://rvm.io)
* [PostgreSQL](http://www.postgresql.org)
* [ImageMagick](http://www.imagemagick.org)
* [PhantomJS](http://phantomjs.org)
* [Node.js](http://nodejs.org)
* [curl](http://curl.haxx.se)
* [git](http://git-scm.com)
* [ack](http://beyondgrep.com)
* [tree](http://linux.die.net/man/1/tree)
* [git bash completion](https://github.com/git/git/blob/master/contrib/completion/git-completion.bash)
* [custom command prompt](https://github.com/neerajdotname/dotfiles/blob/master/bash/command_prompt.bash)
* [memcached](http://memcached.org)
* [bashmarks](https://github.com/huyng/bashmarks)
* [Heroku toolbelt](https://toolbelt.heroku.com)


#### Brought to you by

![BigBinary](http://bigbinary.com/assets/common/logo.png)

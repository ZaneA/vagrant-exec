vagrant-exec
===============

Vagrant plugin to execute commands within the context of VM synced directory.

[![Gem Version](https://badge.fury.io/rb/vagrant-exec.png)](http://badge.fury.io/rb/vagrant-exec)
[![Build Status](https://secure.travis-ci.org/p0deje/vagrant-exec.png)](http://travis-ci.org/p0deje/vagrant-exec)

Description
-----------

You will probably use the plugin if you don't want to SSH into the box to execute commands simply because your machine environment is already configured (e.g. I use ZSH and TextMate bundles to run specs/features).

Example
-------

```shell
➜ vagrant exec pwd
/vagrant
```

Installation
-------

```shell
➜ vagrant plugin install vagrant-exec
```

Configuration
-------------

The root directory can be configured using Vagrantfile.

```ruby
Vagrant.configure('2') do |config|
  config.vm.box = 'precise32'
  config.exec.folder = '/custom'
end
```

You can also enable bundler to prepend each command with `bundle exec` (note, that it won't be done for commands like `bundle install`).

```ruby
Vagrant.configure('2') do |config|
  config.vm.box = 'precise32'
  config.exec.bundler = true
end
```

Acceptance tests
----------------

Before running features, you'll need to bootstrap box.

```shell
➜ rake features:bootstrap
➜ rake features:run
```

Note on Patches/Pull Requests
-----------------------------

* Fork the project.
* Make your feature addition or bug fix.
* Add tests for it. This is important so I don't break it in a future version unintentionally.
* Commit, do not mess with rakefile, version, or history. (if you want to have your own version, that is fine but bump version in a commit by itself I can ignore when I pull)
* Send me a pull request. Bonus points for topic branches.

Copyright
---------

Copyright (c) 2013-2013 Alex Rodionov. See LICENSE for details.
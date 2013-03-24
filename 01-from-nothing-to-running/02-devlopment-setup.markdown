## Setting up a Development Environment

### Mac OS 
Go here: http://www.moncefbelyamani.com/how-to-install-xcode-homebrew-git-rvm-ruby-on-mac/

#### Postgresql 
Partly from [this blog post](http://www.moncefbelyamani.com/how-to-install-postgresql-on-a-mac-with-homebrew-and-lunchy/)
Next you need to install [postgresql](http://www.postgresql.org/). The first step is to install [homebrew](http://mxcl.github.com/homebrew/). 

First make sure the homebrew is up to date

	$ brew update
	
Then check homebrew's health

	$ brew doctor
	
Then install postgresql itself

	$ brew install postgresql
	
If this your 

### Windows
Just like on Mac OS the fine folks at [EngineYard](http://EngineYard.com) made it easy. Just go to [the RailsInstaller website](http://railsinstaller.org/) and download and install.


Please note that devloping on Windows is not widely supported in the world Ruby and the like so the best might to might be to use a Virtual Machine, also called a VM, and install Linux on it and follow the Linux directions. In order to this you first need something like [VirtualBox](ttps://www.virtualbox.org/) which is free or use a paid product [Vmware Workstation](http://www.vmware.com/products/workstation/new.html). I am going show how create a VM with VrtualBox.

#### Using a VM
First download the ISO, disk image, of distribution of choice. Here are few choices that will work with this tutorial:

* [Ubuntu](http://www.ubuntu.com)
* [Linux Mint](http://www.linuxmint.com/)
* [Debian](http://www.debian.org)

The really isn't a large difference between each of the distribution. If this is your first Linux experience then the official suggestion is Ubuntu. 

First Open VirtualBox.

Then Click *Create New*


### Linux
1. Still cURL

	$ sudo apt-get install curl
	
2. Install RVM

	$ \curl -L https://get.rvm.io | bash -s stable

	$ source ~/.rvm/scripts/rvm
	
3. Install Packages
See which ones you by running

	$ rvm requirements

In this output look for a paragraph like this

> Additional Dependencies:
> # For Ruby / Ruby HEAD (MRI, Rubinius, & REE), install the following:
>  ruby: /usr/bin/apt-get install build-essential openssl libreadline6 libreadline6-dev curl git-core zlib1g zlib1g-dev libssl-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt-dev autoconf libc6-dev ncurses-dev automake libtool bison subversion pkg-config

**DO NOT** copy what is above run `rvm requirements` run that command and look for output like that.

4. Install Git
Follow the Instructions in the [ProGit Book](http://www.git-scm.com/book/en/Getting-Started-Installing-Git).

5. Setup Ruby
Install the lastest version Ruby.

	$ rvm install 1.9.3

6. Install RubyGems
Ruby on Rails needs this to be installed.

	$ rvm rubygems current

7. Install Rails
Time to install Rails itself.

	$ gem install rails
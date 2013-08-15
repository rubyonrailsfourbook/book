## Setting up a Development Environment
In this section I will cover how to setup Ruby on Rails for Mac OS, Linux, and Windows. Each Operation System is different so just skip to the section to that portions to your operation system.


### Mac OS 
The first setup of setting up for Mac OS computer for running Ruby on Rails is to download XCode from the app store. Please note that XCode is a large program and may take a while to install depending on your internet connection.

After you have installed XCode next you need to install the XCode Command Line tools. Do you the first opening XCode and then Preferences.

![](images/chapter_2/xcode_prefs.png)

Then go to the Downalods tab

![](images/chapter_2/downloads_tab.png)

Then Click "Install" on the command line tools.

![](images/chapter_2/xcode-cmt.png)

After you install the commandline tools next you need to install homebrew. Open the Terminal and run the command below and follow the instructions.  This will install the homebrew package management system. 

	$ ruby -e "$(curl -fsSL https://raw.github.com/mxcl/homebrew/go)"

After this make sure that brew is running by running `brew doctor` and follow any instructions that it outputted. 

Then the following commands to install Apple GCC compiler. This will used by some gems

	 $ brew tap homebrew/dupes
 	 $ brew install apple-gcc42
 	 $ sudo ln -s /usr/local/bin/gcc-4.2 /usr/bin/gcc-4.2

Then next install RVM. RVM, Ruby Version Manager, that helps you manage different ruby versions.

	$ \curl -L https://get.rvm.io | bash -s stable --ruby --rails

The following command install the latest version ruby on rails.

#### PostgreSQL 
I have found that the that simplest solution for using PostgreSQL on Mac OS to use [Postgres.app](http://http://postgresapp.com/) from the fine folks at [Heroku](https://heroku.com). The setups for setting this up is simple. First download it from the Postgres.app website. Then unzip the zip file. Move the icon from the Downloads folder to the Applications folder then double click on the icon. Then you are up and running.


### Windows
Just like on Mac OS the fine folks at [EngineYard](http://EngineYard.com) made it easy. Just go to [the RailsInstaller website](http://railsinstaller.org/) and download and install.


Please note that developing on Windows is not widely supported in the world Ruby and the like so the best might to might be to use a Virtual Machine, also called a VM, and install Linux on it and follow the Linux directions. In order to this you first need something like [Vagrant](http://www.vagrantup.com) which is free and open source. Then use a project like INSERT CHEF RAILS VAGRANT PROJECT HERE to install all the needed software.	

### Linux Install
1. instill cURL

	$ sudo apt-get install curl
	
2. Install RVM

	$ \curl -L https://get.rvm.io | bash -s stable --ruby --rails

	$ source ~/.rvm/scripts/rvm
	
3. Install Packages
See which ones you by running

	$ rvm requirements

In this output look for a paragraph like this

> Additional Dependencies:
>  For Ruby / Ruby HEAD (MRI, Rubinius, & REE), install the following:
>  ruby: /usr/bin/apt-get install build-essential openssl libreadline6 libreadline6-dev curl git-core zlib1g zlib1g-dev libssl-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt-dev autoconf libc6-dev ncurses-dev automake libtool bison subversion pkg-config

**DO NOT** copy what is above run `rvm requirements` run that command on your own and look for the output like that.

4. Install Git
Follow the Instructions from the [ProGit Book](http://www.git-scm.com/book/en/Getting-Started-Installing-Git).



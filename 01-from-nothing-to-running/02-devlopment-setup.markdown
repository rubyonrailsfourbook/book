## Setting up a Development Environment

### Mac OS
The fine folks at [EngineYard](http://EngineYard.com) made this.
[RailsInstaller](http://railsinstaller.org/)

### Windows
The fine folks at [EngineYard](http://EngineYard.com) made this.
[RailsInstaller](http://railsinstaller.org/)

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
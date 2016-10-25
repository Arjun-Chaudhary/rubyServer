#Ruby Server
This server will gather data from Aircasting mobile application in Real Time and send it to mysql database for insertion in real time.
It's a restful server where we are making HTML requests in form of JSON request.

###About

These are the steps to install a ruby server in order to recieve data from Aircasting Android App and then storing that data to MySQL.
###Developing

For a [Debian](http://debian.org)/[Ubuntu](http://ubuntu.com) system, the easiest way to start is:

**RVM prerequisites**

`sudo apt-get install bzip2 curl subversion git-core -y`

**Install RVM**

`curl -L https://get.rvm.io | bash -s`

**RVM & app requirements**

`sudo apt-get install build-essential openssl libreadline6 libreadline6-dev curl git-core zlib1g zlib1g-dev libssl-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt-dev autoconf libc6-dev ncurses-dev automake libtool bison subversion pkg-config imagemagick mysql-server libmysqlclient-dev redis-server libgsl0-dev nodejs -y`

**install ruby**

```
rvm install 2.0.0
rvm use 2.0.0
```

**install bundler**

`gem install bundler`

**clone sources**

```
git clone https://github.com/Arjun-Chaudhary/COMP90019.git aircasting
cd aircasting
cp config/database.yml.example config/database.yml
```

**bundle dependencies**

`bundle install`

**create database**

`bundle exec rake db:create db:migrate`

**run sidekiq**

`bundle exec sidekiq -d`

**run application, by default starts at [localhost:3000](http://localhost:3000)**

`bundle exec rails server`

### Tests

**run tests**

```
bundle exec rspec
bundle exec rake spec:javascript
```
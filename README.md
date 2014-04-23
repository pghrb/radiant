## Welcome to Radiant

Radiant is a no-fluff, open source content management system designed for
small teams. It is similar to Textpattern or MovableType, but is a general
purpose content management system (not just a blogging engine).

[![Build Status](https://secure.travis-ci.org/radiant/radiant.png?branch=1.x)](http://travis-ci.org/radiant/radiant)

Radiant features:

* An elegant user interface
* The ability to arrange pages in a hierarchy
* Flexible templating with layouts, snippets, page parts, and a custom tagging
  language (Radius: http://radius.rubyforge.org)
* A simple user management/permissions system
* Support for Markdown and Textile as well as traditional HTML (it's easy to
  create other filters)
* An advanced plugin system
* Operates in two modes: dev and production depending on the URL
* A caching system which expires pages every 5 minutes
* Built using Ruby on Rails
* And much more...

## License

Radiant is released under the MIT license and is copyright (c) 2006-2009
John W. Long and Sean Cribbs. A copy of the MIT license can be found in the
LICENSE file.

## Installation and Setup

Radiant is a traditional Ruby on Rails application, meaning that you can
configure and run it the way you would a normal Rails application.

See the INSTALL file for more details.

### Installation of a Prerelease

As Radiant nears newer releases, you can experiment with any prerelease version.

Install the prerelease gem with the following command:

    $ gem install radiant --prerelease

This will install the gem with the prerelease name, for example: ‘radiant-0.9.0.rc2’.

### Upgrading an Existing Project to a newer version

1. Update the Radiant assets from in your project:

    $ rake radiant:update

2. Migrate the database:

    $ rake production db:migrate

3. Restart the web server

## Development Requirements

To run tests on radiant itself:

1. Edit the Gemfile and uncomment the lines that tell you to do so for working on radiant itself.
1. Run `TRAVIS=1 bundle`.
1. If using postgres run (for other DBs see bin/ci/before_script):

        psql -c 'create database radiant_test;' -U postgres
        cp spec/ci/database.postgresql.yml config/database.yml

1. Set up the database by running:

        RAILS_ENV=test bundle exec rake db:migrate
        RAILS_ENV=test bundle exec rake db:migrate:extensions

1. And finally run the tests with:

        RAILS_ENV=test bundle exec rake spec --trace

No, I don't know why this requires you to run the tests in the test environment explicitly. But go ahead and try it without that, you'll see.

## Support

The best place to get support is on the mailing list:

http://radiantcms.org/mailing-list/

Most of the development for Radiant happens on Github:

http://github.com/radiant/radiant/

The project wiki is here:

http://wiki.github.com/radiant/radiant/


Enjoy!

--
The Radiant Dev Team
http://radiantcms.org

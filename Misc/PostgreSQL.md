Local PostgreSQL
====

PostgreSQL is an open source object-relational database system. It has been under active development since 1996, runs on all major operating systems, with support for foreign keys, joins, views, triggers, and stored procedures. PostgreSQL is also [ACID compliant](http://en.wikipedia.org/wiki/ACID).

PostgreSQL is notably [well-supported on the Heroku Platform](https://www.heroku.com/postgres), and available as a beta product under [Amazon’s RDS product](http://aws.amazon.com/rds/postgresql/). For local development on your own server, follow the directions below.

Installation
----

Like MySQL (but unlike SQLite) PostgreSQL runs as a separate system process. It must be started before use, and can be connected to via the local IP address [*127.0.0.1*](http://en.wikipedia.org/wiki/Localhost).

### Mac

[Postgres.app](http://postgresapp.com) is the easiest way to install a local version of PostgreSQL on the Mac.

> Just download, drag to the applications folder, and double-click.

As a perk, Postgres.app ships with the excellent [PostGIS spatial extension](http://postgis.net) and complete [GDAL](http://www.gdal.org/index.html) and [OGR](http://www.gdal.org/ogr/index.html) utilities.

### Linux (Ubuntu)

To install PostgreSQL on Ubuntu Linux, follow [Ubuntu’s installation instructions](https://help.ubuntu.com/community/PostgreSQL#Installation):

> To install use the command line and type:
> 
>     $ sudo apt-get install postgresql postgresql-contrib
> 
> This will install the latest version available in your Ubuntu release and the
> commonly used add-ons for it.

To use PostgreSQL with any Ruby app that uses the [pg gem](https://bitbucket.org/ged/ruby-pg/wiki/Home), you will also need to install libpq-dev:

    $ apt-get install libpq-dev

After Installation
----

With PostgreSQL installed, you may want to create a new database for your project, and a user who can connect to that database. PostgreSQL provides the commands `createuser` and `createdb` for this purpose; `psql` is the command line client. To create a user named “janedoe” who owns the database “doedb” and connect as that user, follow the instructions below for your OS.

The new database will be available to your application. If your application requires a database URL, it will look something like *postgres://janedoe:password@127.0.0.1/doedb*.

### Mac

With Postgres.app, these commands will be located in a directory named `/Applications/Postgres.app/Contents/Versions/9.3/bin` (or similar, depending on the version number).

You can connect to PostgreSQL easily using the Postgres.app elephant menu:

![Screen capture of Postgres.app elephant menu](images/Postgres.app.jpg)

Then use [create user](http://www.postgresql.org/docs/9.0/static/sql-createuser.html) and [create database](http://www.postgresql.org/docs/9.0/static/sql-createdatabase.html) to generate the user:

    # CREATE USER janedoe PASSWORD 'pass';
    # CREATE DATABASE doedb OWNER=janedoe;

### Linux

On Linux, the commands will be available globally, but the creation of the new user will need to be done by `postgres`, the owner the PostgreSQL installation:

    $ sudo -u postgres createuser -P janedoe
    $ sudo -u postgres createdb -O janedoe doedb
    $ psql -h 127.0.0.1 -U janedoe doedb

To use PostgreSQL with a Ruby on Rails app on a development machine, it's recommended to create a database user (without a password) whose name matches your OS username, and to set the [authentication method](http://www.postgresql.org/docs/9.3/static/auth-methods.html) to `trust` in `pg_hba.conf`. Refer to [this gist](https://gist.github.com/m-mujica/5695856) for more details.


AYGNI?
----

Are you going to need a local version of PostgreSQL? If you are using an [object-relational mapper](http://en.wikipedia.org/wiki/Object-relational_mapping) such as [SQLAlchemy](http://www.sqlalchemy.org), it will do its best to hide database-specific implentation details from your application. It’s likely that you may be able to run a development build of your application using [SQLite](https://sqlite.org), which requires no installation or separate process and comes pre-installed with an increasing number of programming languages.

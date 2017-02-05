**This documentation is being deprecated!**
Please update your links to [here](https://wiki.codeforamerica.org)
Future changes will be made from [this github repository](https://github.com/codeforamerica/cfa-wiki)


Ruby on Rails
=============

[Ruby on Rails](https://rubyonrails.org) is an open-source web framework that's optimized for programmer happiness and sustainable productivity.

Many Rails apps may have project-specific install instructions covered in their README, but this guide covers the general steps needed for most Rails apps, and gives context for those steps.

### 1. Follow the Ruby howto

First, follow the instructions in [Ruby.md](Ruby.md) to install Ruby and RVM (the Ruby Version Manager).

### 2. Install Ruby dependencies with bundler

Run:

    bundle install

to install the Ruby dependencies (called "gems") for the project, which are listed in the `Gemfile`.

### 3. Database configuration

Most Rails applications will use SQLite or Postgres when in development mode. Apps using SQLite generally require no configuration.

You can configure the application to use your local database credentials in the `config/database.yml` file.

### 4. Database setup

You can set up the database by running:

    bundle exec rake db:setup

(This actually runs three separate commands — `db:create`, `db:migrate`, and `db:seed` which gets your database all setup.)


### 5. Running the app

Lastly, you can run the app with:

    bundle exec rails s

Or if you want to access a console (REPL) for the app, you can run:

    bundle exec rails c


## Deploying to Heroku

Heroku has a [really good guide to get your Rails app deployed](https://devcenter.heroku.com/articles/getting-started-with-rails4).


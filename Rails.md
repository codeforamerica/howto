Ruby on Rails
=============

From [rubyonrails.org](https://rubyonrails.org): Ruby on Rails is an open-source web framework that's optimized for programmer happiness and sustainable productivity. It lets you write beautiful code by favoring convention over configuration.

Install
-------

Since you've followed the install instructions in [Ruby.md](https://github.com/codeforamerica/howto/blob/master/Ruby.md), you will have rubygems installed.

Use rubygems to install rails:

    $ gem install rails


Create Project
--------------

    $ rails new path/to/your/new/application
    $ cd path/to/your/new/application
    $ rails server

Your project is available at: [http://localhost:3000](http://localhost:3000)

Recommended Configuration
-------------------------

Use [bundler](http://bundler.io/) It offers more sophisticated gem management than just using rubygems and it ensures that gem versions are the same across all environments.

Bundler creates a Gemfile and a Gemfile.lock file in the root of your project. For info on what these files are and how to use them

Use [unicorn](http://unicorn.bogomips.org/) as your web server. You must use unicorn if you want to deploy your application to Heroku. Heroku offers [instructions](https://devcenter.heroku.com/articles/getting-started-with-rails4#webserver) on how to configure unicorn to work locally and to work on Heroku.

Use [RSpec](http://rspec.info/) for unit testing. Also, unit test your application.

Use either [Cucumber](https://github.com/cucumber/cucumber) or [Steak](https://github.com/cavalle/steak) for acceptance testing. Also, acceptance test your application.

Strongly Suggested Usage
------------------------

Rails by default comes with Haml templating. Haml tends to add more overhead and confusion than benefit. It's suggested to stick with erb for views.

Deploy to Heroku
----------------
Heroku has a really good [guide](https://devcenter.heroku.com/articles/getting-started-with-rails4) to get your rails app deployed


Just for Your Information
-------------------------
You can disable the asset pipeline when creating app via:
    rails new myappname --skip-sprockets
    
Or, add in your `config/application.rb`:
    config.assets.enabled = false

You must use the asset pipeline when deploying to heroku.

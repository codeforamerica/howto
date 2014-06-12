Procfile
========

Procfiles provide a way to run web applications that consist of one or more processes.
Developed by David Dollar of Heroku, Procfiles are most commonly used with the Ruby library
[Foreman](http://blog.daviddollar.org/2011/05/06/introducing-foreman.html):

> [Foreman](http://github.com/ddollar/foreman) is an attempt to make this easier.
> Using foreman you can declare the various processes that are needed to run your
> application using a Procfile.
> 
>     web:    bundle exec thin start -p $PORT
>     worker: bundle exec rake resque:work QUEUE=*
>     clock:  bundle exec rake resque:scheduler
> 
> To get started, simply run gem install foreman. If your project is using both
> Bundler and Foreman, launching it should be as simple as
> 
>     $ bundle install
>     $ foreman start

Ruby is [not the only way](https://github.com/ddollar/foreman#ports) to use Procfiles.
[Honcho](https://github.com/nickstenning/honcho) is an excellent Python-based alternative
that will work with the Python libraries already on your Mac or Linux environment.
[Norman](https://github.com/josh/norman) is a Node.js port,
[forego](https://github.com/ddollar/forego) uses the [Go language](http://golang.org),
and [shoreman](https://github.com/hecticjeff/shoreman) is written in bash script.

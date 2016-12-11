Jekyll
======

[Jekyll](http://jekyllrb.com) is a popular [static site generator](http://staticsitegenerators.net).
It helps you to convert plain and specially-structured files and templates into easily-deployable
statically hosted websites. If you use [Github Pages](https://pages.github.com), you’re using Jekyll.
Andrew Munsell’s [Jekyll By Example Tutorial](https://www.andrewmunsell.com/tutorials/jekyll-by-example/tutorial)
is an excellent introduction to creating Jekyll websites.

Install
-------

Start by [installing Ruby](Ruby.md).

Next, [install Jekyll itself](http://jekyllrb.com/docs/installation/):

> The best way to install Jekyll is via RubyGems. At the terminal prompt, simply run the following command to install Jekyll:
> 
>     $ gem install jekyll

Use
---

Build a site [using the `build` command](http://jekyllrb.com/docs/usage/):

> The Jekyll gem makes a jekyll executable available to you in your Terminal window. You can use this command in a number of ways:
> 
>     $ jekyll build
>     # => The current folder will be generated into ./_site
>     
>     $ jekyll build --destination <destination>
>     # => The current folder will be generated into <destination>
>     
>     $ jekyll build --source <source> --destination <destination>
>     # => The <source> folder will be generated into <destination>
>     
>     $ jekyll build --watch
>     # => The current folder will be generated into ./_site,
>     #    watched for changes, and regenerated automatically.

Serve a site using the `serve` command:

    jekyll serve
    # Then open http://localhost:4000/

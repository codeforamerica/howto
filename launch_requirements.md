**This documentation is being deprecated!**
Please update your links to [here](https://wiki.codeforamerica.org)
Future changes will be made from [this github repository](https://github.com/codeforamerica/cfa-wiki)


Requirements to Launch a New Application
========================================

Requirements Checklist:
----------------------

1. The application has a build
  - There is comprehensive test coverage that includes both [unit](http://www.extremeprogramming.org/rules/unittests.html) and [integration (also known as acceptance)](http://www.extremeprogramming.org/rules/functionaltests.html) level tests that **do not** hit the Internet. It is highly recommended to practice [Test Driven Development](http://www.extremeprogramming.org/rules/testfirst.html). Here are some testing guides:
    - [Ruby on Rails](http://guides.rubyonrails.org/testing.html)
    - [Ruby with Sinatra](http://www.sinatrarb.com/testing.html)
    - [Python](http://docs.python-guide.org/en/latest/writing/tests/)
  - The build is being run by a continuous integration platform. CfA currently uses [travis](http://www.travis-ci.org)

2. The application is being monitored
  - The build is included on [project monitor](http://project-monitor.codeforamerica.org/)
  - The application has been added to [engine light](http://engine-light.codeforamerica.org/)

3. The application has undergone a security audit
  - A member of the tech team, along with the application developers, will ensure that the application does not expose any personally identifiable or sensitive information or could expose personally identifiable or sensitive information if the application is compromised.
  - A member of the tech team, along with the application developers, will ensure the application protects against basic UI vulnerabilities, such as the [OWASP to 10](https://www.owasp.org/index.php/Top_10_2013-Top_10)

4. The application has undergone a client-side performance audit
  - A member of the tech team will check over the front-end aspects. A list of frontend checks can be found [here](http://frontendtest.com/checklist/) 
    Example checks:
    + Correct expected behaviour (buttons, tabs, forms submit, links are correct etc.)
    + Spelling mistakes
    + Layout/formatting issues
    + CSS and JS are minified and gzipped
    + Cross browser/device support
  - Usability testing should occur to confirm that the application works as intended with its audience.

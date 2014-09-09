heroku-robot-example
====================

An example project that shows how to run Robot Framework tests on Heroku

## Setting up


Clone the content of this repository to your Heroku app's repository.

Configure your Heroku app to use an external buildpack.

`heroku config:add BUILDPACK_URL=https://github.com/ddollar/heroku-buildpack-multi.git`

This allows you to use separate buildpacks during building your
app/Robot Framework test execution. The used buildbpacks in this
project are for Phantomjs and Python. The builpacks are listed in the
.buildpacks file where you can add additional ones if needed.

Push the new files to your Heroku app repository. 

You should now be able to run your first Robot Framework test case
from Heroku.

`heroku run tests`


## File explanation

* bin/test 

  Script to run the tests. Sets paths for Phantomjs and possible Robot
  libraries. Calls Robot with phantomjs as browser and the default
  test case as parameter.


* RobotTests

  Example Robot Framework test project. You can start with modifying
  this for your first test.

* requirements.txt 

  Required by Heroku. This defines the necessary Python libraries
  required by your Heroku app. Specifically Robot Framework and
  Selenium2 libraried needed for running web tests with Robot
  Framework.

  You'll probably want to at least update the versions of these for
  you project.

* Procfile 

  Defines a Heroku process type, in this case the tests to run using
  Robot Framework.


		   
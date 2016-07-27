# Perfect Heroku Buildpack

[![Gitter](https://badges.gitter.im/PerfectlySoft/PerfectDocs.svg)](https://gitter.im/PerfectlySoft/PerfectDocs?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)

Reference and documentation for the Perfect library.

## Issues

We are transitioning to using JIRA for all bugs and support related issues, therefore the GitHub issues has been disabled.

If you find a mistake, bug, or any other helpful suggestion you'd like to make on the docs please head over to [http://jira.perfect.org:8080/servicedesk/customer/portal/1](http://jira.perfect.org:8080/servicedesk/customer/portal/1) and raise it.

A comprehensive list of open issues can be found at [http://jira.perfect.org:8080/projects/ISS/issues](http://jira.perfect.org:8080/projects/ISS/issues)


A Heroku Buildpack for Swift + Perfect
Packaged by Shao Miller <swiftcode@synthetel.com>
2016-03-22 13:25:42 UTC

This "Buildpack" makes dependencies available at the /app/.delta/ path.  These
include Swift and Perfect.

Your project must have the following file and directory structure:
  src/                : Contains your source code
  src/makefile        : Invoked by the Buildpack
  src/Package.perfect : Informs Buildpack about your Perfect project

Your project will have the following structure after building:
  PerfectLibraries/   : Modules for Perfect Server can go in here
  webroot/            : Files for Perfect Server stand-alone can go in here

Your project should have the following structure:
  Procfile            : This informs Heroku about processes to deploy

This Buildpack will move into your src/ directory, then invoke 'make', followed
by 'make install'.  See the following example Github project:

  https://github.com/PerfectlySoft/Perfect-Heroku-Buildpack-Example

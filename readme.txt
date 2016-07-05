A Heroku Buildpack for Swift3 + Perfect
Packaged by Shao Miller <swiftcode@synthetel.com>
2016-03-22 13:25:42 UTC
Updated for Swift3 by Tim Taplin <taplin@accesstelluride.com>
2016-06-26 10:47:55 MST

This "Buildpack" makes dependencies available at the /app/.delta/ path.  These
include Swift and Perfect.

#### All below items will be updated for Swift3 and SPM compatibility:
Your project must have the following file and directory structure:
  Sources/                : Contains your source code
  Package.swift : Informs Buildpack about your Perfect project

Your project will have the following structure after building:
  Packages/           : Dependency files will be here
  .build/             : Executables will be here

Your project should have the following structure:
  Procfile            : This informs Heroku about processes to deploy

This Buildpack will move invoke 
swift build -Xlinker -L/app/.test/usr/lib -Xcc -I/app/.test/usr/include/

### There are several possible updates/improvements that might need to be made.
### Possibly Heroku config variables can be used 
###       to determine a list of libraries to be installed by apt-get
###       to determine which Swift toolchain to install
###       to determine whether the swift toolchain is a production/preview/development build (affects the path used)
### Currently installs libraries for basic functionality only, no db connectors support

###

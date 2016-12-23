# Capsule File
==============

A capsule file tells [codecapsule] what projects/repositories to clone and their storing location.
It's an INI-style file, based on the following example:

   [project-name]
   remote=git@github.com:example/project.git
   path=project-one

   [databits]
   remote=git@github.com:example/databits.git
   path=data/databits

Using the above example as if it were a proper capsule file, if you'd run `codecapsule sync` in an initialised directory, the directory structure would look like this when done:

/home/user/initialised-directory/.codecapsule/codecapsule-util    # codecapsule commands directory
/home/user/initialised-directory/.codecapsule/capsule             # the above file
/home/user/initialised-directory/project-one                      # the first project
/home/user/initialised-directory/data/databits                    # the databits project

INI Format and Keys
-------------------

The format is an INI-style file so that additional properties can be associated with each project.
Section names are just identifiers and are used for display purposes only.
Comments are supported with either or `#` or `;` as the first character on the line.


### remote

This lists the remote URL to use for the initial git clone.

Examples:

   [Sample Project]
   remote=http://github.com/example/project.git
   path=project/

### path

The path is the destination directory where the repository should be checked out to.

Examples:

   [WebServer Configs]
   ; Installs this repository to config/webserver/
   remote=http://github.com/example/webserver-config.git
   path=config/webserver/


   [codecapsule]: https://github.com/prexco/codecapsule.git

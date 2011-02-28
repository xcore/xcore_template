This repository provides a template for new repositories on the XCore
open source github repository site.
To create a new repository using this template
use the following steps. These steps assume that you have a
new, empty repository on the XCore open source github site (see 
https://github.com/xmos/Community/wiki/Repository-management on how 
to do this)

Requirements:

* Git installed locally
* Python installed locally (version 2.7)
* An new empty github repository
* A github account with ssh keys generated (see "Generate a Keypair" at http://help.github.com/)

Steps:

1. Create a working directory (or use an existing one with other repositories in).

1. If it does not already exist, clone the xcommon repository from github::
     git clone ssh://git@github.com/xmos/xcommon.git

1. Clone the xmos_template repository from github::

     git clone ssh://git@github.com/xmos/xmos_template.git

1. Use the rename_repository script to rename xmos_template to your repository name. Run this script from the working directory above the xmos_template directory. For example to change the name to my_repo::

     python xcommon/util/rename_repository.py xmos_template my_repo

1. You can now change into the new my_repo directory::

     cd my_repo

   this will have its origin pointing at xmos/my_repo on github.

1. Either copy/modify the app_template, plugin_template and module_template directories to contain the source code for the apps, modules and plugins of the repository. Or copy in existing apps and modules from elsewhere. Make sure that any copied in directories have Makefiles/module_build_infos in a similar form to the template examples. Pay particular attention to the include part of an application Makefile. It should look like this::

   # Use the main Makefile from module_xcommon
   -include ../module_xcommon/build/Makefile.common
   -include ../../xcommon/module_xcommon/build/Makefile.common

1. Once you have your specific modules set up you can remove the template directories, and rename the README_template.rst file to README.rst.
 
1. Now you can stage all the new files and do the repositories first commit and push it to a newly created github repo with the same name. You can do that like this::

	git add -A
	git commit -am "First commit"
	git push -u origin master

That's all...
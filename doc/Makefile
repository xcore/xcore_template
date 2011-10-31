# Change this line to reflect your repo name
#
REPO=../../xcore_template

#
# Change this line to title your repo documentation
#
SPHINX_PROJECT_NAME=XCore Template

#
# Set the version number to something appropriate, eg
# VERSION=0v1
#
VERSION=0v1

#
# Add all module names here eg
# DOXYGEN_DIRS=$(REPO)/module_bob $(REPO)/module_john
#
DOXYGEN_DIRS=

#========== Nothing needs changing beyond this point
SOURCE_INCLUDE_DIRS=$(REPO)
XDOC_DIR ?= ../../xdoc
include $(XDOC_DIR)/Makefile.inc

all: html pdf
	@if [ ! -d $(REPO)_gh_pages ] ; then echo '**** no gh_pages checked out ****'; exit 0; else cp -r _build/html/* $(REPO)_gh_pages/; cp -r _build/html/.doctrees $(REPO)_gh_pages/; echo 'HTML files copied to $(REPO)_gh_pages'; echo 'Now go to $(REPO)_gh_pages, add, commit, and push to publish the documentation'; fi

# Shell to use with Make
SHELL := /bin/bash

# Set important Paths
PROJECT := # Set to your project name
LOCALPATH := $(CURDIR)/$(PROJECT)
PYTHONPATH := $(LOCALPATH)/
PYTHON_BIN := $(VIRTUAL_ENV)/bin

# Export targets not associated with files
.PHONY: test coverage pip virtualenv clean publish

# Clean build files
clean:
	find . -name "*.pyc" -print0 | xargs -0 rm -rf
	-rm -rf htmlcov
	-rm -rf .coverage
	-rm -rf build
	-rm -rf dist
	-rm -rf $(PROJECT).egg-info

# Targets for testing
test:
	$(PYTHON_BIN)/nosetests -v --with-coverage --cover-package=$(PROJECT) --cover-inclusive --cover-erase tests

# Publish to gh-pages
# Make sure to change the prefix to the subdirectory of your docs build
publish:
	git subtree push --prefix=docs origin gh-pages

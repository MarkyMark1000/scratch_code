#Add any comments on this here

#Ensure the script is run as bash
SHELL:=/bin/bash

#Set help as the default for this makefile.
.DEFAULT: help

.PHONY: help
help:
	@echo ""
	@echo "PROJECT HELP:"
	@echo "make               		- this prints out the help for this makefile."
	@echo "make help          		- this prints out the help for this makefile."
	@echo "Clean:"
	@echo "make clean	    		- DANGER - remove coverage and node_modules"
	@echo "make setup	    		- setup yarn for testing."
	@echo "Code Formatting:"
	@echo "make prettier	    		- prettier"
	@echo "make eslint	    		- eslint"
	@echo "Tests:"
	@echo "make test	    		- Unittest"
	@echo "Coverage:"
	@echo "make cov-clean			- Remove coverage directory"
	@echo "make cov	    		- Run coverage"
	@echo ""

.PHONY: clean
clean:
	@echo ""
	@echo "*** clean ***"
	@echo ""
	(rm -rf ./coverage; rm -rf ./node_modules;)
	@echo ""

.PHONY: setup
setup:
	@echo ""
	@echo "*** setup ***"
	@echo ""
	(yarn;)
	@echo ""

.PHONY: prettier
prettier:
	@echo ""
	@echo "*** prettier ***"
	@echo ""
	( yarn prettier )
	@echo ""

.PHONY: eslint
eslint:
	@echo ""
	@echo "*** eslint ***"
	@echo ""
	( yarn eslint )
	@echo ""

.PHONY: test
test:
	@echo ""
	@echo "*** unittest ***"
	@echo ""
	( yarn test )
	@echo ""

.PHONY: cov-clean
cov-clean:
	@echo ""
	@echo "*** coverage-clean ***"
	@echo ""
	( rm -rf ./coverage;)
	@echo ""

.PHONY: cov
cov:
	@echo ""
	@echo "*** coverage - also creates a coverage directory ***"
	@echo ""
	( yarn cov )
	@echo ""
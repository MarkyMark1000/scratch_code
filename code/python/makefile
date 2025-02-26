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
	@echo "make clean	    		- DANGER - remove .py files, venv, coverage etc."
	@echo "make venv	    		- create a virtual environment with requirements."
	@echo "Code Formatting:"
	@echo "make isort	    		- Apply isort"
	@echo "make flake8	    		- Apply flake8"
	@echo "make doc		    	- Apply pydocstring"
	@echo "make mypy		    	- Apply mypy"
	@echo "make bandit			- Apply bandit"
	@echo "Tests:"
	@echo "make test	    		- Unittest"
	@echo "Coverage:"
	@echo "make cov-clean			- Remove coverage directory"
	@echo "make cov	    		- Run coverage"
	@echo "make cov-html	    		- Build html coverage report"
	@echo ""

.PHONY: clean
clean:
	@echo ""
	@echo "*** clean ***"
	@echo ""
	(rm -rf venv; rm -rf *.ics; rm -rf *.pyc; find . -type d -name  "__pycache__" -exec rm -r {} +; rm -rf .mypy_cache; rm -rf .pytest_cache; rm -rf ./htmlcov; rm -rf .coverage;)
	@echo ""

.PHONY: venv
venv:
	@echo ""
	@echo "*** venv ***"
	@echo ""
	(python3 -m venv venv; source venv/bin/activate; pip install --upgrade pip; pip install -r requirements.txt;)
	@echo ""

.PHONY: isort
isort:
	@echo ""
	@echo "*** isort ***"
	@echo ""
	( isort . )
	@echo ""

.PHONY: flake8
flake8:
	@echo ""
	@echo "*** make virtual env ***"
	@echo ""
	(flake8 . )
	@echo ""

.PHONY: doc
doc:
	@echo ""
	@echo "*** make virtual env ***"
	@echo ""
	( pydocstyle . )
	@echo ""

.PHONY: mypy
mypy:
	@echo ""
	@echo "*** apply mypy ***"
	@echo ""
	( mypy . )
	@echo ""

.PHONY: bandit
bandit:
	@echo ""
	@echo "*** apply bandit ***"
	@echo ""
	( bandit -c pyproject.toml -r . )
	@echo ""

.PHONY: test
test:
	@echo ""
	@echo "*** unittest ***"
	@echo ""
	( pytest .)
	@echo ""

.PHONY: cov-clean
cov-clean:
	@echo ""
	@echo "*** coverage-clean ***"
	@echo ""
	( rm -rf ./htmlcov; rm -rf .coverage; )
	@echo ""

.PHONY: cov
cov:
	@echo ""
	@echo "*** coverage ***"
	@echo ""
	( pytest --cov )
	@echo ""

.PHONY: cov-html
cov-html:
	@echo ""
	@echo "*** html report ***"
	@echo ""
	( pytest --cov --cov-report=html:htmlcov )
	@echo ""
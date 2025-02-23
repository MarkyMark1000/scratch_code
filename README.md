# OVERVIEW

This is intended to be a very simple disposable piece of code where I can create a single
file for solving online problems and a single file for unit tests associated with that
problem.   My core language is Python, but I tend to extend it so that it can use other
languages.

I also intend git to be usable within this directory (although not as a remote repo that
gets updated), so that the code can be stored.

## PYTHON

- Main code is expected to work around the main branch, so checkout this branch.
- Go into the python directory using the terminal.   Clean and recreate the virtual
  environment using these commands:
  ```
  cd code/python
  make clean
  make venv
  source venv/bin/activate
  ```

  Test to make sure it works correctly using this:
  ```
  make test
  ```

  You then use standard git to create a new branch, commit changes to the branch etc.

  Once finished, delete the unused branches.
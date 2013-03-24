# virtualenv for Python

- slug: virtualenv-for-python
- date: 2013-03-24
- tags: python, www-dev, gnu-linux

------------------

Install:

	sudo pip install virtualenv

or, if you have Python 3.x installed, and want to use Python 2.x:

	sudo pip2 install virtualenv

Create a new project:

	virtualenv <project_name>

Activate project:

	source <project_name>/bin/activate

Deactivate project _(must be run from within active project)_:

	deactivate

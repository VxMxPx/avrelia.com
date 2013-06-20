# virtualenv for Python

- slug: virtualenv-for-python
- date: 2013-03-24
- category: tech
- tags: python, www-dev, gnu-linux

------------------

Install:

````bash
sudo pip install virtualenv
````

or, if you have Python 3.x installed, and want to use Python 2.x:

````bash
sudo pip2 install virtualenv
````

_If you don't have pip, you can install it with:_

````bash
# For python 2.x
sudo pacman -S python2-pip

# For python 3.x
sudo pacman -S python-pip
````

Create a new project:

````bash
virtualenv <project_name>
````

Activate project:

````bash
source <project_name>/bin/activate
````

Deactivate project _(must be run from within active project)_:

````bash
deactivate
````

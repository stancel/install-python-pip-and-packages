install_python_pip_and_packages
=========

Ansible role to install [pyenv](https://github.com/pyenv/pyenv) and then use it to install multiple versions of Python, Pip and any needed pip packages.

Requirements
------------

None

Role Variables
--------------

Python, Documentation and Graphviz Packages Needed for Installation and Documentation Sites

```
python_packages:
  - build-essential
  - libssl-dev
  - libffi-dev
  - ca-certificates
  - python
  - python-dev
  - python-openssl
  - python-pip
  - python-pip-whl
  - python-setuptools
  - python-virtualenv
  - python3
  - python3-dev
  - python3-distutils
  - python3-openssl
  - python3-pip
  - python3-setuptools
  - python3-virtualenv
  - python3-venv
  - graphviz
  - graphviz-doc
  - libgraphviz-dev
  - libgv-php7
  - python3-graphviz
  - python3-gv
  - xdot
  - pandoc
```

PyEnv Info to Install and Setup

```
pyenv_version: v1.2.15
python27_version: 2.7.17
python34_version: 3.4.10
python35_version: 3.5.8
python36_version: 3.6.9
python37_version: 3.7.5
pyenv_command: "pyenv global {{ python37_version }}"
```

Pip Packages Needed to Install. This will need to be done for each version of Python installed if using other than the global version

```
pip_packages:
  - sphinx
  - sphinx-autobuild
  - sphinx-intl
  - sphinx_rtd_theme
  - recommonmark
  - pymysql
```

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```
	- hosts: your_webserver
	  vars_files:
	    - vars/main.yml
	  roles:
	    - stancel.install_python_pip_and_packages
```

License
-------

GPLv3

Author Information
------------------

[Brad Stance](https://github.com/stancel)

install_python_pip_and_packages
=========

Ansible role to install [pyenv](https://github.com/pyenv/pyenv) and then use it to install multiple versions of Python, Pip and any needed pip packages.

Requirements
------------

None

Role Variables
--------------

List of home directories of users where pyenv shims and PATH are installed into the `.bashrc` file. Do not include a trailing slash - ex. `/home/myuser` instead of `/home/myuser/`. The default includes the root user's home directory - `/root`. 
This list is required and cannot be blank.

```
users_home_directories_to_install_pyenv_for:
  - /root
```

Python, Documentation and Graphviz Packages Needed for Installation and Documentation Sites. The defaults are listed below.

```
python_packages:
  - build-essential
  - libssl1.0-dev
  - libffi-dev
  - zlib1g-dev
  - libbz2-dev
  - libreadline-dev
  - libsqlite3-dev
  - wget
  - curl
  - llvm
  - libncurses5-dev
  - libncursesw5-dev
  - xz-utils
  - liblzma-dev
  - python-openssl
  - git
  - ca-certificates
  - python
  - python-dev
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

PyEnv Info to Install and Setup. Defaults listed below.

```
pyenv_version: v1.2.15
python27_version: 2.7.17
python34_version: 3.4.10
python35_version: 3.5.8
python36_version: 3.6.9
python37_version: 3.7.5
pyenv_command: "pyenv global {{ python37_version }} system"
```

Pip Packages Needed to Install. This will need to be done for each version of Python installed if using other than the global version. Defaults listed below.

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

or 

```
	- hosts: your_server 
	  vars:
		pyenv_version: v1.2.15
		users_home_directories_to_install_pyenv_for:
		  - /home/{{ ansible_user }}
		  - /home/myuser
		pip_packages:
          - sphinx
          - sphinx-autobuild
          - sphinx-intl
          - sphinx_rtd_theme
          - recommonmark
          - pymysql
        pyenv_command: "pyenv global {{ python37_version }} {{ python36_version }} system"
	  roles:
	    - stancel.install_python_pip_and_packages
```


License
-------

GPLv3

Author Information
------------------

[Brad Stancel](https://github.com/stancel)

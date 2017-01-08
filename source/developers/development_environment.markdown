---
layout: page
title: "Set up Development Environment"
description: "Set up your environment to start developing for Home Assistant."
date: 2014-12-21 13:32
sidebar: true
comments: false
sharing: true
footer: true
---

You'll need to set up a development environment if you want to develop a new feature or component for Home Assistant. Read on to learn how to set up.

* Visit the [Home Assistant repository](https://github.com/home-assistant/home-assistant) and click **Fork**.
* To avoid conflicts and interdepency related issues, it's recommended that you setup a virtual environment for you Home Assistant development environment, details below.

```bash
$ git clone https://github.com/YOUR_GIT_USERNAME/home-assistant.git
$ cd home-assistant
$ git remote add upstream https://github.com/home-assistant/home-assistant.git
$ script/setup
```
### {& linkable_title Setting up in a virtual environent %}
* Ensure you have the correct Python Dev environment installed: 'sudo apt-get install python-pip python3-dev'
* Consider setting up a virtual environment using [`venv`](https://docs.python.org/3.4/library/venv.html) before running the setup script. Note by using `venv` as the folder for the virtual environment, this is already included in the `.gitignore` file your will pull as part of your foked code base.
e.g:
'''
bash
$ git clone https://github.com/YOUR_GIT_USERNAME/home-assistant.git
$ cd home-assistant
$ git remote add upstream https://github.com/home-assistant/home-assistant.git
$ virtualenv -p python3 venv 
$ source venv/bin/activate
$ script/setup
'''
* On Windows, you can use `python setup.py develop` instead of the setup script.

* Run `hass` to invoke your local installation.

### {% linkable_title Logging %}

By default logging in home-assistant is tuned for operating in
production (set to INFO by default, with some modules set to even less
verbose logging levels).

You can use the [logger](/components/logger/) component to adjust
logging to DEBUG to see even more details about what is going on.

### {% linkable_title Developing on Windows %}

If you are using Windows as a development platform, make sure that you have the correct Microsoft Visual C++ build tools installed. Check the [Windows Compilers](https://wiki.python.org/moin/WindowsCompilers) section on the [Python website](https://www.python.org/) for details. Validation using `tox` will fail if this is not done correctly.

Also, make sure to install or upgrade the `setuptools` Python package. It contains compatibility improvements and adds automatic use of compilers:

```bash
$ pip install --upgrade setuptools
```

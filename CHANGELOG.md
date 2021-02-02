<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Change log](#change-log)
  - [1.0.4 - 2021-02-02](#104---2021-02-02)
    - [Changed](#changed)
  - [1.0.3 - 2021-01-30](#103---2021-01-30)
    - [Added](#added)
  - [1.0.2 - 2021-01-16](#102---2021-01-16)
    - [Added](#added-1)
  - [1.0.1 - 2021-01-08](#101---2021-01-08)
    - [Added](#added-2)
  - [1.0.0 - 2020-12-21](#100---2020-12-21)
    - [Added](#added-3)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# Change log

This file contains al notable changes to the VIM Ansible role.

This file adheres to the guidelines of <http://keepachangelog.com/>. Versioning follows [Semantic Versioning](http://semver.org/).

## 1.0.4 - 2021-02-02

### Changed

- The magic variables ansible have been changed to their equivalent to ansible_facts.<br>
  The reason for the change is because so far in the ansible settings **inject_facts_as_vars = True**,
  but it is recommended to change it to **False**.

  Ansible facts are available inside the ansible_facts.X dictionary
  namespace. This setting maintains the behaviour which was the default prior
  to 2.5, duplicating these variables into the main namespace, each with a
  prefix of 'ansible_'

  This variable is set to True by default for backwards compatibility. It
  will be changed to a default of 'False' in a future release.

## 1.0.3 - 2021-01-30

### Added

- Installation via package or pathogen plugin:
  - ansible-vim

## 1.0.2 - 2021-01-16

### Added

- Installation via package or pathogen plugin:
  - mikrotik-syntax

## 1.0.1 - 2021-01-08

### Added

- Support for Fedora 31, 32, 33 and 34
- Support for Debian "Bullseye"
- Support for Ubuntu "Bionic", "Focal" and "Groovy"
- Installation via package or pathogen plugin:
  - toml-syntax
  - Solarized Colorscheme

## 1.0.0 - 2020-12-21

First release!

### Added

- Support for Debian 10 "Buster"
- Support for CentOS 8
- Installation via package or pathogen plugin:
  - powerline
  - pathogen
  - airline
  - airline-themes
  - nerdtree
  - gitgutter
  - floaterm
  - jinja2-syntax
  - fugitive

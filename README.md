[![Molecule Test](https://github.com/tonipamies/ansible-role-vim/workflows/Molecule%20Test/badge.svg)](https://github.com/tonipamies/ansible-role-vim/actions?query=workflow%3AMolecule%20Test+branch%3Amain+event%3Apush)
[![Ansible-lint rules explanation](https://img.shields.io/badge/Ansible--lint-rules%20table-blue.svg)](https://ansible-lint.readthedocs.io/en/latest/default_rules.html)
[![Ansible-lint](https://img.shields.io/badge/Ansible--lint-Passed-brightgreen)](https://ansible-lint.readthedocs.io/)
[![pre-commit](https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit&logoColor=white)](https://github.com/pre-commit/pre-commit)
[![CodeFactor](https://www.codefactor.io/repository/github/tonipamies/ansible-role-vim/badge)](https://www.codefactor.io/repository/github/tonipamies/ansible-role-vim)
<br>
[![Galaxy VIM](https://img.shields.io/ansible/role/52632)](https://galaxy.ansible.com/tonipamies/vim)
[![Galaxy VIM](https://img.shields.io/ansible/quality/52632)](https://galaxy.ansible.com/tonipamies/vim)
[![Galaxy VIM](https://img.shields.io/ansible/role/d/52632)](https://galaxy.ansible.com/tonipamies/vim)

# Ansible role `ansible-role-vim`

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

- [Description](#description)
- [Linux distributions supported](#linux-distributions-supported)
- [Requirements](#requirements)
- [Role Variables](#role-variables)
  - [Basic configuration](#basic-configuration)
  - [Custom pathogen plugins](#custom-pathogen-plugins)
- [Examples](#examples)
  - [Example Playbook](#example-playbook)
  - [Example Task](#example-task)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Description

An Ansible role to install and configure vim in linux distributions.  Specifically, the responsibilities of this role are to:

- Installs vim packages and [pathogen](https://github.com/tpope/vim-pathogen) plugins from the official distribution repositories
- Installs [pathogen](https://github.com/tpope/vim-pathogen) plugin manager
    - Configuration file [pathogen.vim](templates/etc/vim/pathogen.vim.j2)
- Installs [powerline](https://powerline.readthedocs.io/en/latest/)
- Installs [airline](https://github.com/vim-airline/vim-airline)
    - Configuration file [airline.vim](templates/etc/vim/airline.vim.j2)
- Installs [airline-themes](https://github.com/vim-airline/vim-airline-themes)
    - Configuration file [vim-airline-themes.vim](templates/etc/vim/vim-airline-themes.vim.j2)
- Installs [nerdtree](https://github.com/preservim/nerdtree)
    - Configuration file [nerdtree.vim](templates/etc/vim/nerdtree.vim.j2)
- Installs [gitgutter](https://github.com/airblade/vim-gitgutter)
    - Configuration file [vim-gitgutter.vim](templates/etc/vim/vim-gitgutter.vim.j2)
- Installs [floaterm](https://github.com/voldikss/vim-floaterm)
    - Configuration file [vim-floaterm.vim](templates/etc/vim/vim-floaterm.vim.j2)
- Installs [fugitive](https://tpope.io/vim/fugitive.git)
    - Configuration file [fugitive.vim](templates/etc/vim/fugitive.vim.j2)
- Installs [solarized colorscheme](https://github.com/altercation/vim-colors-solarized)
    - Configuration file [vim-colors-solarized.vim](templates/etc/vim/vim-colors-solarized.vim.j2)
- Installs [jinja2-syntax](https://github.com/Glench/Vim-Jinja2-Syntax)
    - Configuration file [vim-jinja2-syntax.vim](templates/etc/vim/vim-jinja2-syntax.vim.j2)
- Installs [toml-syntax](https://github.com/cespare/vim-toml)
    - Configuration file [vim-toml-syntax.vim](templates/etc/vim/vim-toml-syntax.vim.j2)
- Installs [mikrotik-syntax](https://github.com/zainin/vim-mikrotik)
    - Configuration file [vim-mikrotik-syntax.vim](templates/etc/vim/vim-mikrotik-syntax.vim.j2)
- Installs [ansible-vim](https://github.com/pearofducks/ansible-vim)
    - Configuration file [vim-ansible.vim](templates/etc/vim/vim-ansible.vim.j2)
- Default vim configuration on [vimrc.local](templates/etc/vim/vimrc.local.j2)

Refer to the [change log](CHANGELOG.md) for changes in each release.

## Linux distributions supported

- CentOS 8
- Debian 10 Buster
- Debian 11 Bullseye
- Fedora 31
- Fedora 32
- Fedora 33
- Fedora 34
- Fedora 35
- Ubuntu 18.04 Bionic
- Ubuntu 20.04 Focal

## Requirements

- Ansible 2.9
- Git for install the pathogen plugins (Installation included in the role itself)
- On CentOS EPEL Repository (Installation included in the role itself)

## Role Variables

None of the variables below are required. When not defined by the user, the [default values](defaults/main.yml) are used.

### Basic configuration

| Variable                       | Default         | Comments                                                                             |
| :---                           | :---            | :---                                                                                 |
| `color`                          | 'darkblue'      | The default colorschema<br>One of: blue, darkblue, default, delek, desert, elflord, evening, industry, koehler,<br>morning, murphy, pablo, peachpuff, ron, shine, slate, solarized, torte, zellnet |
| `airline_theme`| 'luna' | The default airline theme<br>One of: alduin, angr, atomic, aurora, ayu_mirage, badcat, badwolf, base16,<br>base16_3024, base16_apathy, base16_ashes, base16_atelierdune,<br>base16_atelierforest, base16_atelierheath, base16_atelierlakeside<br>base16_atelierseaside, base16_bespin, base16_brewer, base16_bright,<br>base16_chalk, base16_classic, base16_codeschool, base16_colors,<br>base16_default, base16_eighties, base16_embers, base16_flat,<br>base16_google, base16_grayscale, base16_greenscreen, base16_harmonic16,<br>base16_hopscotch, base16_isotope, base16_londontube, base16_marrakesh,<br>base16_mocha, base16_monokai, base16_nord, base16_ocean,<br>base16_oceanicnext, base16_paraiso, base16_pop, base16_railscasts,<br>base16_seti, base16_shapeshifter, base16_shell, base16_solarized,<br>base16_spacemacs, base16_summerfruit, base16_tomorrow, base16_twilight,<br>base16color, behelit, biogoo, bubblegum, cobalt2, cool, dark,<br>dark_minimal, distinguished, dracula, durant, fairyfloss, hybrid,<br>hybridline, jellybeans, jet, kalisi, kolor, laederon, light, lucius,<br>luna, minimalist, molokai, monochrome, murmur, night_owl, onedark,<br>papercolor, peaksea, powerlineish, qwq, raven, ravenpower, serene,<br>sierra, silver, simple, sol, solarized, solarized_flood, term,<br>term_light, tomorrow, ubaryd, understated, vice, violet, wombat,<br>xtermlight, zenburn<br>|
|`custom_pathogen_plugins`|[]|List of dicts specifying the pathogen plugins to be added. See [below](#Custom-pathogen-plugins) for details|
|`backup_config_files`|false| When `true`, this role will backup all the configurations files before to do any change|

### Custom pathogen plugins
A list of pathogen plugins to be added and are defined with a dict containing the fields:
  - `name` (required) The name of the pathogen plugin
  - `url` (required) The git url of the pathogen plugin
  - `enabled` (required) `true` install the pathogen plugin
  - `config_file` (optional) a vim config file to be included in vimrc with specificconfiguration for this plugin

The following example installs [nerdcommenter](https://github.com/preservim/nerdcommenter)
```yaml
- custom_pathogen_plugins:
  - name: nerdcommenter
    url: 'https://github.com/preservim/nerdcommenter'
    enabled: true
    config_file: 'roles/common/templates/etc/vim/nerdcommenter.vim.j2
```
## Examples
### Example Playbook
```yaml
---
- hosts: all
  gather_facts: true
  remote_user: ansible
  become: true

  roles:
    - role: vim
      vars:
        - backup_config_files: true
        - color: ron
        - airline_theme: vice
        - custom_pathogen_plugins:
          - name: nerdcommenter
            url: 'https://github.com/preservim/nerdcommenter'
            enabled: true
            config_file: 'roles/common/templates/etc/vim/nerdcommenter.vim.j2'
```
### Example Task
```yaml
#
# Install Vim Packages
#
- name: INCLUDE ROLE | Install Vim Packages & Configure it
  include_role:
    name: vim
  vars:
    - backup_config_files: true
    - color: ron
    - airline_theme: vice
    - custom_pathogen_plugins:
      - name: nerdcommenter
        url: 'https://github.com/preservim/nerdcommenter'
        enabled: true
        config_file: 'roles/common/templates/etc/vim/nerdcommenter.vim.j2'
  when:
    - vim_for_sysadmins is defined
    - vim_for_sysadmins | bool
  tags:
    - install
    - configure
```

Example of file nerdcommenter.vim.j2

```html+jinja
{{ ansible_managed | comment }}
"
" Nerdcommenter configuration
"
"
" Create default mappings
let g:NERDCreateDefaultMappings = 1

" Add spaces after comment delimiters by default
let g:NERDSpaceDelims = 1

" Use compact syntax for prettified multi-line comments
let g:NERDCompactSexyComs = 1

" Align line-wise comment delimiters flush left instead of following code indentation
let g:NERDDefaultAlign = 'left'

" Set a language to use its alternate delimiters by default
let g:NERDAltDelims_java = 1

" Add your own custom formats or override the defaults
let g:NERDCustomDelimiters = { 'c': { 'left': '/**','right': '*/' } }

" Allow commenting and inverting empty lines (useful when commenting a region)
let g:NERDCommentEmptyLines = 1

" Enable trimming of trailing whitespace when uncommenting
let g:NERDTrimTrailingWhitespace = 1

" Enable NERDCommenterToggle to check all selected lines is commented or not
let g:NERDToggleCheckAllLines = 1
```

# Setup a Chef Repository

Read through all the instructions. Determine which items are done by each person in the team and which are done once for the whole team. Break up work into discrete chunks and ensure that everyone does part of the "1 per team" items. Some items have dependencies on earlier work, so make sure that you allocate work appropriately.

## Fork team repo (Everyone)

Fork your team's repo into your account, and clone it back to your workstation.

* Click on "Fork" and fork into your personal account.
* git clone git@github.com:USER/TEAM-repo.git

### Update docs/skills.md (Notetaker)

* add notes taken during the team discussion to skills.md within the repo.

## Generate the chef repo (1 per team)

In this exercise we are creating a chef-repo. The chef-repo will hold the global policy items as well as all of the cookbooks tha

* cd TEAM-repo
* chef generate repo chef-repo
* git add chef-repo
* git commit -m "Initial creation of chef repo"
* git remote -v
* git push origin master


## Discuss with your team your branching strategy. (Team discussion)

* update docs/branch.md (Notetaker) with the team decided strategy

## Create application cookbook (1 per team)

* chef generate cookbook app

## Install Apache via a Recipe (1 per team)

### Create feature branch or use your branching strategy

* git checkout -b install_apache

### Include apache2 cookbook from supermarket

[Apache2 Cookbook](https://supermarket.chef.io/cookbooks/apache2)

* open `app/recipes/default.rb` in editor
* add `include_recipe 'apache2'`
* save file
* open `app/metadata.rb` in editor
* add `depends 'apache2'`
* save file

### Save your changes and commit back to the team's repository

_NOTE_

Make sure that you are not just commiting back to your local repository on the node, or to your fork of the repository.


## Install MySQL via a Recipe (1 per team)

### Create feature branch or use your branching strategy

* git checkout -b install_mysql

### Include mysql cookbook from supermarket

* open `app/recipes/default.rb` in editor
* add `include_recipe 'app::mysql_service'`
* save file
* open `app/recipes/mysql_service.rb` in editor
* add a mysql_config and mysql_service using examples from [mysql cookbook README](https://github.com/chef-cookbooks/mysql)
* open `app/metadata.rb` in editor
* add 

```
depends 'mysql', '~> 6.0'
```
* save `app/metadata.rb` file

### Save your changes and commit back to the team's repository

_NOTE_

Make sure that you are not just commiting back to your local repository on the node, or to your fork of the repository.

## EXTRA CREDIT: Customize website via a Recipe (1 per team)

### Create feature branch or use your branching strategy

* git checkout -b custom_website

### Use template resource

Read up on the template resource on the [Chef Docs site](http://docs.chef.io/resources.html#template) if you don't remember what a template is.

* open `app/recipes/default.rb` in editor
* use template resource
* save file
* create template
* open `app/metadata.rb` in editor, update version
* save file

### Save your changes and commit back to the team's repository

_NOTE_

Make sure that you are not just commiting back to your local repository on the node, or to your fork of the repository.


## Outcome 

You should have an updated TEAM-repo with

* updated docs/branch.md, skills.md
* chef-repo
* app cookbook

You might also have

* customized website 



# Setup a Chef Repository

Read through all the instructions. Determine which items are done by each person in the team and which are done once for the whole team. Break up work into discrete chunks and ensure that everyone does part of the "1 per team" items. Some items have dependencies on earlier work, so make sure that you allocate work appropriately.

## Generate the chef repo (1 per team)

In this exercise we are creating a chef-repo. The chef-repo will hold the global policy items as well as any cookbooks created in this workshop. Generally, when using with a Chef server you choose between one of two strategies. 

1. Monolithic Workflow - 1 chef-repo containing everything that maps to 1 repo in source control.
2. 1 cookbook per repo + policy only chef-repo. 


* cd ~/wd/TEAM-repo
* chef generate repo chef-repo
* git add chef-repo
* git commit -m "Initial creation of chef repo"
* save your changes and commit back to team's repo

## Create application cookbook (1 per team)

This step depends on the chef-repo existing.

* cd ~/wd/TEAM-repo/chef-repo/cookbooks
* chef generate cookbook app
* git add app
* git commit -m "creation of cookbook app"
* save your changes and commit back to team's repo

## Install Apache via a Recipe (1 per team)

This step depends on the cookbook app being created.

### Create feature branch or use your branching strategy

* git checkout -b install_apache

* open `~/wd/TEAM-repo/chef-repo/cookbooks/app/recipes/default.rb` in editor
* add  

```
package 'httpd'

service 'httpd' do
  action [ :enable, :start ]
end

```

#### Use kitchen and docker to test your recipe

* cd ~/wd/TEAM-repo/chef-repo/cookbooks/app
* Update ~/wd/TEAM-repo/chef-repo/cookbooks/app/.kitchen.yml
 * Change driver name from `vagrant` to `docker`
 * Remove the line `- name: ubuntu-12.04`
 * Update the centos-6.5 line to include driver_config to forward port 80

```
platforms:
  - name: centos-6.5
    driver_config:
      forward:
      - 80:80
```
 * Save the file
* kitchen converge (This will take a few minutes!)

#### If all is well, Save your work!

How do you know if your recipe worked? Kitchen converge finishes without errors, and you have a port up and running. You can check by browsing directly to the node because you have set up port forwarding!

 * cd ~/wd/TEAM-repo/chef-repo/cookbooks/
 * git add app
 * git commit -m "install and configure apache"
 * save your changes and commit back to team's repo


## Install MySQL via a Recipe (1 per team)

### Create feature branch or use your branching strategy

* git checkout -b install_mysql

### Include mysql cookbook from supermarket

[Supermarket](https://supermarket.chef.io) is the Chef community site. Before using community cookbooks in your environment, always inspect the cookbook. You run the code with root privileges!

* open `~/wd/TEAM-repo/chef-repo/cookbooks/app/recipes/default.rb` in editor
* add `include_recipe 'app::mysql_service'`
* save file

#### Using mysql cookbook

We will use the mysql cookbook. The [mysql cookbook](https://github.com/chef-cookbooks/mysql) is a library cookbook, and contains no recipes. It only has resources that we can use that extend the available resources to manage. We will use the mysql_service resource. You can also read the examples in the [mysql cookbook README](https://github.com/chef-cookbooks/mysql) to understand how to use the other available mysql resources.

* open `~/wd/TEAM-repo/chef-repo/cookbooks/app/recipes/mysql_service.rb` in editor
* add  

```
mysql_service 'joengo' do
  port '3306'
  version '5.5'
  initial_root_password 'banana'
  action [:create, :start]
end
```

* open `app/metadata.rb` in editor
* add 

```
depends 'mysql', '~> 6.0'
```
* save `app/metadata.rb` file

#### Use kitchen and docker to test your recipe

* cd ~/wd/TEAM-repo/chef-repo/cookbooks/app
* Update ~/wd/TEAM-repo/chef-repo/cookbooks/app/.kitchen.yml
 * Change driver name from `vagrant` to `docker`
 * Remove the line `- name: ubuntu-12.04`
 * Update the centos-6.5 line to include driver_config to forward port 80

```
platforms:
  - name: centos-6.5
    driver_config:
      forward:
      - 80:80
```
 * Save the file
* kitchen converge (This will take a few minutes!)

#### If all is well, Save your work!

How do you know if your recipe worked? Kitchen converge finishes without errors, and you have a port up and running. You can check by browsing directly to the node because you have set up port forwarding!

 * cd ~/wd/TEAM-repo/chef-repo/cookbooks/
 * git add app
 * git commit -m "install and configure mysql"
 * save your changes and commit back to team's repo

## Verify your development environment is consistent (Everyone)

Depending on which part of the work you did, you should make sure that your node is working as expected.

* git pull origin master
* cd ~/wd/TEAM-repo/chef-repo/cookbooks/app
* update your .kitchen.yml to match as above
* kitchen converge
* kitchen login 
 * Password: kitchen

## Outcome 

You should have an updated TEAM-repo with

* updated docs/branch.md, skills.md
* chef-repo
* app cookbook

 

### (Optional) Include apache2 cookbook from supermarket

[Supermarket](https://supermarket.chef.io) is the Chef community site. Before using community cookbooks in your environment, always inspect the cookbook. You run the code with root privileges!

The Apache2 cookbook will allow you to set up virtual hosts. You could use this cookbook instead of the simple recipe we have made to install apache.

[Apache2 Cookbook](https://supermarket.chef.io/cookbooks/apache2)

* open `~/wd/TEAM-repo/chef-repo/cookbooks/app/recipes/default.rb` in editor
* add `include_recipe 'apache2'`
* save file
* open `~/wd/TEAM-repo/chef-repo/cookbooks/app/metadata.rb` in editor
* add `depends 'apache2'`
* save file


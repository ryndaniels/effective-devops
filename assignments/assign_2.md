# Setup a Chef Repository

## Create repository on GitHub (1 per team)

In this exercise we are creating a chef-repo. The chef-repo will hold the global policy items as well as all of the cookbooks that your team will create.

* Click on "New repository".
* Name the repository chef-repo-yyyymmdd.
* git clone git@github.com:ORGANIZATION/chef-repo-yyyymmdd.git
* chef generate repo chef-repo-yyyymmdd
* cd chef-repo-yyyymmdd
* git add .
* git commit -m "Initial creation of chef repo"
* git remote -v
* git push origin master


## Fork repository from GitHub

* Click on "Fork" and fork into your personal account.
* git clone git@github.com:USER/chef-repo-yyyymmdd.git
* Update README.md with your name




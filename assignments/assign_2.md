# Setup a Chef Repository

## Fork team repo

Fork your team's repo into your account, and clone it back to your workstation.

* Click on "Fork" and fork into your personal account.
* git clone git@github.com:USER/TEAM-repo.git

### Update docs/skills.md (Notetaker)

* add notes taken during the team discussion to skills.md within the repo.

## Generate the chef repo (1 per team)

In this exercise we are creating a chef-repo. The chef-repo will hold the global policy items as well as all of the cookbooks that your team will create.

* chef generate repo chef-repo
* git add chef-repo
* git commit -m "Initial creation of chef repo"
* git remote -v
* git push origin master


## Discuss with your team your branching strategy.

* update docs/branch.md (Notetaker) with the team decided strategy



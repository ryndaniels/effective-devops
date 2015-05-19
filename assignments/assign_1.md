# Verify Local Environment

## Overview

In this exercise each participant configures and tests a local development environment.

## Create a GitHub identity

* If you don't already have a github account, create one.
* Browse to http://github.com. Supply a username, email address, and password.
* Free plan is fine. Other plans allow you to have private repo.

## Share your GitHub identity with your group

* Jennifer Davis, iennae
* Katherine Daniels, kdaniels

## Create GitHub Organization (1 per team)

In this exercise, each team will create a single github organization and invite the individuals on the team and Jennifer and Katherine to the organization.

* From the main dashboard, upper left click on your name.
* Click on the "Create organization"
* Choose your organization name based off of your team name.
* Billing email off of a team member's email address.
* Open Source plan
* Click on Create organization.
* Invite Jennifer, Katherine, and the rest of the team to the organization.

## Accept invitation to GitHub Organization

* Visit https://github.com/ORGANIZATION
* Accept invitation.

## Create a repo within your organization (1 per team)

In this exercise, you will create a new repository for the team called "initial-git-test".

* Click on "New repository".
* In the repository name "initial-git-test".
* Click on "Initialize this repository with a README".
* Click on Create repository.

## Verify access to repo.

* git clone git@github.com:ORGANIZATION/initial-git-test.git
* update README.md with your name
* git add README.md
* git commit -m "added name"
* git push origin master

### Problems

* Are you getting an "Error: Permission to ORG/REPO denied to user" error?
 * Verify that you have been added to the organization to be able to write to repositories.


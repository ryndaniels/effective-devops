slidenumbers: true

=======
# [fit] Effective Devops:
# [fit] Collaboration and Tools
## Jennifer Davis & Katherine Daniels

---
# Introductions

---
# Jennifer Davis

* Automation Engineer, Chef
* Co-author of "Effective Devops"
* DevOpsDays SV Organizer
* Sparkly Devops Princess
* CoffeeOps Organizer

![fit](https://raw.githubusercontent.com/kdaniels/effective-devops/master/images/effectivedevops.jpg)
![fit](https://raw.githubusercontent.com/kdaniels/effective-devops/master/images/devopsprincess.png)
![fit](https://raw.githubusercontent.com/kdaniels/effective-devops/master/images/coffee_ops.jpg)

---
# Katherine Daniels

* Web Operations Engineer, Etsy
* Co-author of "Effective Devops"
* DevopsDays NYC Organizer
* Ship Show Podcast Co-host
* Ladies Who Linux NYC Co-organizer


![fit](https://raw.githubusercontent.com/kdaniels/effective-devops/master/images/cat.jpg)
![fit](https://raw.githubusercontent.com/kdaniels/effective-devops/master/images/beer.jpg)
![fit](https://raw.githubusercontent.com/kdaniels/effective-devops/master/images/effectivedevops.jpg)

---
# Communication and Feedback

Twitter: @sigje, @beerops
Email:

---
# Schedule

* 10:30-11am Morning Break
* 12:30-1:30pm Lunch
* 3-3:30pm Afternoon Break

---
# Expectations

---
# Team Introductions

* Meet your team!
* Identify your team's...
 * Speaker
 * Gatekeeper
 * Notetaker

Time: 15 minutes

---

![fit](https://raw.githubusercontent.com/kdaniels/effective-devops/master/images/effectivedevops.jpg)

---
# What is Devops

---
# Folk Models

---
# Why Devops?

---
# High Performing devops Teams
# are more Agile
## 30X more frequent deployments
## 8000X faster lead times than peers

2014 PuppetLabs State of DevOps Survey

---
# High Performing devops Teams
# are more Reliable
## 2X change success rate
## 12X faster mean time to recovery (MTTR)

2014 PuppetLabs State of DevOps Survey

---
# Five Pillars of Effective Devops

* Collaboration
* Hiring
* Affinity
* Tools
* Scaling

---
# Collaboration: Individuals Working Together

---
# Hiring: Choosing Individuals

---
# Affinity: From Individuals to Teams

---
# Tools: Choosing and Using them

---
# Scaling: Growing Everything Up

---
# Collaboration and Tools


---
# The Devops Compact

---

> A life becomes meaningful when one sees himself or herself as an actor within the context of a story.

-- George Howard


---
# Discussion: Team Intro

* What are motivations?
* What are current beliefs?
* What are current skills? gaps in skills?
Time: 15 minutes

---
# Share: Team Intro
* Team Name:
* Common Motivations?
* Skills? Gaps?

---
# Application Deployment Planning

* OS - Centos

---
# Deming Cycle

* Plan: Identify and Analyze problem
* Do: Develop and Test potential solution
* Check: Measuring effectiveness
* Act: Implement solution

---
# Devops Tools

* Establish local development environment
* Version control
* Automation
 * Infrastructure
 * Sandbox
 * Test and Build

---
# Local Development Environment

* consistent set of tools across the team
* ability to quickly onboard new engineers

---
# Provisioned node - LDE

* AWS instance node
* Chef DK
 * Test Kitchen
 * Ruby
 * ChefSpec, ServerSpec
* Git

---
# [fit] Configuration Management

* process of identifying, managing, monitoring, and auditing a product through its entire life including the processes, documentation, people, tools, software,  and systems.

---
# Version Control

* records changes to files or sets of files stored within the system
* enable revisions
* integrity checking
* collaboration

---
# [fit] Introduction to Git and Workflows

---
# Isolated Development Environments

* not automatically updated
* manually pull upstream commits

---
# Workspace Environment

```
$ git init
$ git add . 
```

adds all files and directories to version control

---
# Commit

```
$ git commit -m "message about commit" -a
```

---
All changes local! How to collaborate?

---
# Show all remotes

```
$ git remote -v 
```

---
# Add remote server

```
$ git remote add NAME URL
```

---
# Update changes to remote directory

```
$ git push REPONAME BRANCH
```

---
# View the branches

```
$ git branch -a
```

---
# Creating the branches

```
$ git checkout -b BRANCHNAME
```

---
# Merging branches

```
$ git merge BRANCH
```
---
# git fetch

* import commits, from remote to local

git checkout master
git log origin/master
git merge origin/master

---

# Different workflows

* feature branch
* gitflow
* forking
* centralized

---

# Pull Requests

* collaboration prior to integration
 * discussion
 * follow up commits

---

# git pull

git pull REMOTE

---
# git pull --rebase

* ensure linear history by preventing unnecessary merge commits

---
# git push remote branch

* transfer commits from a local repo to a remote repo.
* counterpart to git fetch

---
# Assignment 1

* verifying node
* setting up organization
* verifying access to repositories

---
# Infrastructure

* aggregate of applications, configurations, access control, data, compute nodes, network, storage, processes, and people.

---
# Infrastructure Automation

* systems that reduce the burden on people to manage services and increase the quality, accuracy and precision of a service to the consumers of a service

---
# Infrastructure Automation Tools

* chef
* puppet
* ansible

---
# Introduction to Chef


---
# Nodes

---
# Resources

* ingredients of infrastructure
* basic building blocks

---
# Recipes

---
# Cookbooks

---
# Run List

---
# Roles

---
# Environments

---
# Chef

* Chef Server
* Chef Zero


---
# Supermarket

---
# Chef DK

---
# Berkshelf

* Dependency management

---
# Test Kitchen

* included with Chef DK
* Sandbox automation
* Test harness

---
# Test Kitchen

* execute code on one or more platforms
* driver plugins supporting various cloud and virtualization providers

---
# .kitchen.yml

* driver
* provisioner
* platforms
* suites

---
# .kitchen.yml driver

* virtualization or cloud provider

Example: vagrant, docker

---
# .kitchen.yml provisioner

* application to configure the node

Example: chef_zero

---
# .kitchen.yml platforms

* target operating systems

Example: centos-6.5

---
# .kitchen.yml suites

* target configurations

Example:
```
 name:default
   run_list:
   - recipe[apache::default]
   attributes:
```

---
# Kitchen commands (1/2)

* kitchen init
* kitchen list
* kitchen create
* kitchen converge

---
# Kitchen commands (2/2)

* kitchen verify
* kitchen destroy
* kitchen test

---
# Assignment 2

---
# Docker

* images
* registries
* containers

---
# Managing Risk

* test
* small frequent releases

---
# Linting

* ensure code adheres to styles and conventions.
* weave expectations into development
* encourages collaboration

---
# Testing

* documenting objectives and intent
* measuring "done"

---
# Code Correctness

* foodcritic
* rubocop

---
# Integration Tests

* ServerSpec

---
# Rubocop

* ruby linter
* [ruby style guide](https://github.com/bbatsov/ruby-style-guide)
* included with ChefDK

---
# Rubocop Example

```
$ rubocop cookbooks/COOKBOOK1 cookbooks/COOKBOOK2 cookbooks/COOKBOOK4
```
---
# Reading Rubocop Output

```
Inspecting 8 files
CWCWCCCC
```

* `.` means that the file contains no issues
* `C` means a issue with convention
* `W` means a warning
* `E` means an error
* `F` means an fatal error

---
# Disabling Rubocop cops

Any configuration in `.rubocop.yml` is disabled.

To disable string literals:
```
StringLiterals:
  Enabled: false
```
---
# Foodcritic

* chef linter
* [chef style guide](http://foodcritic.io)
* included with ChefDK

---
# Foodcritic Example

```
$ foodcritic cookbooks/setup
```
---
# Reading Foodcritic Output

```
FC008: Generated cookbook metadata needs updating: ./metadata.rb:2
```
---
# ServerSpec

* tests to verify servers functionality
* resource types
 * package, service, user, and many others
* integrates with Test Kitchen
* http://serverspec.org

---
# ServerSpec Generic Form

```
describe "<subject>" do
  it "<description>" do
    expect(thing).to eq result
  end
end
```

---
# ServerSpec Potential Tests

* Is the service running?
* Is the port accessible?
* Is the expected content being served?

---
# ServerSpec Example

```
describe 'apache' do
 it "is installed" do
   expect(package 'apache2').to be_installed
 end
 it "is running" do
   expect(service 'apache2').to be_running
 end
end
```

---
# Reading ServerSpec Output

---

# [fit] Measuring Impact and Value of Change

---

# Impact

---

## Impact on Availability
* Overall site/app availability
* Individual service availability

---

## Impact on Quality
* Service quality (SLAs)
* Visibility of quality

---

(examples of things to measure from our example)

---

# Assignment 5

---

(review)

---





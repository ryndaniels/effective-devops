=======
# [fit] Effective Devops:
# [fit] Collaboration and Tools
## Jennifer Davis & Katherine Daniels

---
# Introductions

---
# Jennifer Davis

---
# Katherine Daniels

---
# Team Introductions

---
# Schedule

* 10:30-11am Morning Break
* 12:30-1:30pm Lunch
* 3-3:30pm Afternoon Break

---
# Expectations

---
# Effective Devops 

---
# What is Devops

---
# Folk Models

---

# Five Pillars of Effective Devops

* Collaboration
* Hiring
* Affinity
* Tools
* Scaling

---
# Collaboration and Tools

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
# The Devops Compact

---
# Team

* Speaker
* Gatekeeper 
* Notetaker

---
# Discussion: Team Intro

* Who is your team?
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

---
# [fit] Introduction to Git and Workflows

---

# Isolated Development Environments

* not automatically updated
* manually pull upstream commits

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

# Serverspec

---

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





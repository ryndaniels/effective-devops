# LAMP Stack

## Overview

In this exercise, every team will update their cookbooks, and add tests for recipes. Generally when pairing, one person will write the test, and then the other person will write the code that repairs the test.

The company has decided to implement a "JoeNGo" web site that will allow for individuals to find a local coffeeshop and meet up friends who have available time on an ad-hoc basis. 

Your company currently uses LAMP stack for other applications. Your team needs to decide based on experience whether to extend off of current standards or introduce new technology into your stack.

You need to plan, implement, and deploy infrastructure code that will allow rapid iteration on the site while also incorporating visual assests from designers, feedback from marketing and sales, while monitoring the costs of the solution.


## Customize website via a Recipe (1 per team)

### Create feature branch or use your branching strategy

* git checkout -b custom_website

### Write a failing test for content

Make sure you base your failing test based on the content you expect to see. 

Two different methods for testing, what's different between them and which do you choose to use to test?

Update `test/integration/default/serverspec/default_spec.rb`:

```ruby
describe file('/var/www/html/index.html') do
  it { should contain('Hello World')}
end
```

OR

Update `test/integration/default/serverspec/default_spec.rb`:

```ruby
describe command('curl -s http://localhost') do
  its(:stdout) { should_not contain('Centos') }
  its(:stdout) { should contain('Hello World') }
end
```
### Verify Test

* kitchen converge
* kitchen verify

### Write the Code

Update `app/recipes/default.rb` with

```ruby
file '/var/www/html/index.html' do
  content "<h1>Hello, World</h1>"
end
```

### Extra Credit: Replace file with template resource

Read up on the template resource on the [Chef Docs site](http://docs.chef.io/resources.html#template) if you don't remember what a template is.

Update `app/recipes/default.rb` with

```ruby
template '/var/www/html/index.html' do
  .....
end
```

* save file
* create template
* open `app/metadata.rb` in editor, update version
* save file

### Save your changes and commit back to the team's repository

_NOTE_

Make sure that you are not just commiting back to your local repository on the node, or to your fork of the repository.

```
git status
git add recipes test
git commit -m "updated content adding tests"
git push origin custom_website
```

## Add tests for earlier features (1 per team)

### Create feature branch or use your branching strategy

* git checkout -b missing_tests

### Identify what tests you should add for mysql and apache

* Update `test/integration/default/serverspec/default_spec.rb`:
* Update `test/integration/default/serverspec/mysql_service_spec.rb`:

### Verify Test

* kitchen converge
* kitchen verify

### Save your changes and commit back to the team's repository

_NOTE_

Make sure that you are not just commiting back to your local repository on the node, or to your fork of the repository.

```
git status
git add test
git commit -m "adding tests"
git push origin missing_tests
```

# Install Java via a Recipe

## Create feature branch

* git checkout -b install_java

## Create application cookbook

* chef generate cookbook app

## Include java cookbook from supermarket

* open `app/recipes/default.rb` in editor
* add `include_recipe 'java'`
* save file
* open `app/metadata.rb` in editor
* add `depends 'java'`
* save file

## Test

* foodcritic .
* rubocop

## Add exclusions to Rubocop config file

* open app/.rubocop.yml in editor
* add

```
Style/SingleSpaceBeforeFirstArg:
    Enabled: false

```
* save file

## Test

Clean up any remaining failures.

* rubocop

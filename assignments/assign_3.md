
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

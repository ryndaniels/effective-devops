# Test

## Linting (Everyone)

* cd ~/wd/TEAM-repo/chef-repo/cookbooks/app
* foodcritic .
* rubocop .

```
$ rubocop cookbooks/app
warning: parser/current is loading parser/ruby21, which recognizes
warning: 2.1.5-compliant syntax, but you are running 2.1.4.
Inspecting 7 files
CC.C..C
```

### Add exclusions to Rubocop config file (Everyone)

* open .rubocop.yml in editor
* add

```
Style/SingleSpaceBeforeFirstArg:
    Enabled: false

```
* save file
* rubocop .

## Integration Tests (Everyone)

* open `test/integration/default/serverspec/default_spec.rb`
* update content

```
require 'spec_helper'

describe 'app::default' do
  it "httpd service is running" do
   expect(service 'httpd').to be_running
 end
end
```

* kitchen verify

Expected Output:

```

[chef@ip-172-31-61-2 app]$ kitchen verify
-----> Starting Kitchen (v1.3.1)
-----> Verifying <default-centos-65>...
       Removing /tmp/busser/suites/serverspec
       Uploading /tmp/busser/suites/serverspec/spec_helper.rb (mode=0664)
       Uploading /tmp/busser/suites/serverspec/default_spec.rb (mode=0664)
-----> Running serverspec test suite
       /opt/chef/embedded/bin/ruby -I/tmp/busser/suites/serverspec -I/tmp/busser/gems/gems/rspec-support-3.2.2/lib:/tmp/busser/gems/gems/rspec-core-3.2.3/lib /opt/chef/embedded/bin/rspec --pattern /tmp/busser/suites/serverspec/\*\*/\*_spec.rb --color --format documentation --default-path /tmp/busser/suites/serverspec

       app::default
         httpd service is running

       Finished in 0.26429 seconds (files took 0.7166 seconds to load)
       1 example, 0 failures

       Finished verifying <default-centos-65> (0m5.41s).
-----> Kitchen is finished. (0m6.28s)

```


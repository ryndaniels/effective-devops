* sudo rpm -i 'http://pkgs.repoforge.org/rpmforge-release/rpmforge-release-0.5.3-1.el6.rf.x86_64.rpm'
* sudo vi /etc/yum.repos.d/rpmforge.repo
    * In the rpmforge-extras section, change 'Enabled = 0' to 'Enabled = 1'
* sudo yum update git

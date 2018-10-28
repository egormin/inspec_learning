### There are some ways to run tests:
***Run test locally:***
```
inspec exec test.rb
```
***Run test on remote host on SSH***
```
inspec exec test.rb -t ssh://user@hostname
```
***Run test on remote windows host on WinRM***
```
inspec exec test.rb -t winrm://Administrator@windowshost --password 'your-password'
```
***Run test on docker container***
```
inspec exec test.rb -t docker://container_id
```
***Run with sudo***
```
inspec exec test.rb --sudo [--sudo-password ...] [--sudo-options ...] [--sudo_command ...]
```
***Run in a subshell***
```
inspec exec test.rb --shell [--shell-options ...] [--shell-command ...]
```
***Run a profile targeting AWS using env vars***
```
inspec exec test.rb -t aws://
```
***or store your AWS credentials in your ~/.aws/credentials profiles file***
```
inspec exec test.rb -t aws://us-east-2/my-profile
```
***Run a profile targeting Azure using env vars***
```
inspec exec test.rb -t azure://
```
***or store your Azure credentials in your ~/.azure/credentials profiles file***
```
inspec exec test.rb -t azure://subscription_id
```
***Run tests from archive:***
```
inspec exec auditd-0.1.0.tar.gz -t ssh://root:password@target
```
***Run tests from git:***
```
inspec exec https://github.com/learn-chef/auditd/releases/download/v0.1.0/auditd-0.1.0.tar.gz -t ssh://root:password@target
```
***Run tests from community profile:***
```
inspec supermarket exec dev-sec/linux-baseline -t ssh://root:password@target
```

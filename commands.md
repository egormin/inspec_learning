### Usefull comansds:

***Get help:***
```
inspec help
```
***Get system details:***
```
inspec detect
```
for remote system:
```
inspec detect -t ssh://user@10.7.44.2
```
***Run tests:***
```
inspec exec /root/auditd
```
for remote system:
```
inspec exec /root/auditd -t ssh://user@10.7.44.2
```
***Shell mode:***
```
inspec shell
```
for remote system:
```
inspec shell -t ssh://user@10.7.44.2
```
***Verify if your profile is free of errors:***
```
inspec check auditd
```
***Archive profile:***
```
inspec archive auditd
```
***Run tests from archive:***
```
inspec exec auditd-0.1.0.tar.gz -t ssh://root:password@target
```
***Run tests from git:***
```
inspec exec https://github.com/learn-chef/auditd/releases/download/v0.1.0/auditd-0.1.0.tar.gz -t ssh://root:password@target
```

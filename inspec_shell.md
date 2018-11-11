### Inspec shell
To enter the interactive session:
```
inspec shell
inspec shell -t ssh://root:password@target
```
***Base shell commands:***
```
help
```
```
help resources
```
```
help [resource]
```
```
help matchers
```
```
exit
```

***Get available methods:***
```
file('/tmp').class.superclass.instance_methods(false).sort
```
or
```
file('/tmp').methods
```

InSpec transforms resource methods to matchers. For example, the `file.directory?` method becomes the `be_directory matcher`.

The `file.readable?` method becomes the `be_readable` matcher.

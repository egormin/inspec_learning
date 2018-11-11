### Inspec DSL description
```
# encoding: utf-8
# copyright: 2018, The Authors

title 'sample section'

# you can also use plain tests
describe file('/tmp') do
  it { should be_directory }
end

# you add controls here
control 'tmp-1.0' do                        # A unique ID for this control
  impact 0.7                                # The criticality, if this control fails.
  title 'Create /tmp directory'             # A human-readable title
  desc 'An optional description...'
  describe file('/tmp') do                  # The actual test
    it { should be_directory }
  end
end
```
`control` is followed by the control's name. Each control in a profile has a unique name

`impact` measures the relative importance of the test and must be a value between 0.0 and 1.0

`title` defines the control's purpose

`desc` provides a more complete description of what the control checks for

`describe` defines the test. Here, the test checks for the existence of the /tmp directory

An InSpec control always contains at least one describe block. However, a control can contain many describe blocks.

```
describe <entity> do
  it { <expectation> }
end
```
An InSpec test has two main components: the ***subject*** to examine and the ***subject's expected state***. Here, `<entity>` is the subject you want to examine, for example, a package name, service, file, or network port. The `<expectation>` part specifies the desired result or expected state, for example, that a port should be open (or perhaps should not be open.)

#### Singular Resource Example
```
describe car(owner: 'Tony Clifton') do
    it { should exist }
    its('license_plate') { should cmp 'MOONMAN' }
    it { should be_classy }
    it { should_not have_check_engine_light_on }
end
```
`car` is a resource. Since we are talking about only one car, it is a singular resource.

`owner` is a resource parameter

`Tony Clifton` is a resource parameter value

`it` test. Use ****it**** to access resource-specific matchers

`its` test. Use its to access properties of the resource

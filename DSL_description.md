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

`its` test. Use ****its**** to access properties of the resource

`license_plate` is a property belonging to the resource

`cmp` is a universal matcher

`MOONMAN` is an expected result

`be_classy` is a resource-specific matcher

`should_not` indicates this is a negated test

`property` is a fact about a resource. Typically, you use the its keyword to access the property and write a test within a describe block, and then use a universal matcher to make assertions about the value of the property.

`resource` represents a category of things on the target you wish to examine

`resource pack` is a type of profile that is used to distribute custom resources

`resource parameters` are information passed to the resource when they are declared

`universal matcher` is a matcher that can be used on the properties of any type of resource

`resource-specific matcher` - is a matcher that operates directly on the resource, as opposed to operating on a property as a universal matcher does

`singular resource` is a resource intended to uniquely identify a single object on the target

`target` is the OS or API on which InSpec is performing audits

`test` is an individual assertion about the state of the resource or one of its properties.

#### Plural Resource Example
```
describe cars.where(color: /^b/) do
  it { should exist }
  its('manufacturers') { should include 'Cadillac' }
  its('count') { should be >= 10 }
end
```
`cars` is a plural resource

`where(color: /^b/)` is a filter statement. Without a filter statement, cars simply selects all the cars in the world

`color` is a filter criterion along with its filter value, /^b/

`include` is a universal matcher. include works with lists, and checks to see if an expected result is present

`be >=` is an operator matcher. It allows you to perform numeric comparisons. All plural resources have a count property

***resource-specific matchers*** operate directly on the resource (Singular Resource), are used with it

***universal matchers*** operate on the properties of the resource (Plural Resources), are used with its, and tend to be very generic, operating on text, numbers, and lists.Plural resources support filter statements

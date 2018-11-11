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

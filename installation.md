**Inspec can be downloaded and installed from the rpm package:**
```
wget https://packages.chef.io/files/stable/inspec/3.0.12/el/7/inspec-3.0.12-1.el7.x86_64.rpm
rpm -ivh inspec-3.0.12-1.el7.x86_64.rpm
```
**Install by script:**
```
curl https://omnitruck.chef.io/install.sh | sudo bash -s – -P inspec
```
**Install via rubygems.org:**
```
yum -y install ruby ruby-devel make gcc gcc-c++
gem install inspec
```
**From docker image:**
```
docker pull chef/inspec
docker run -it --rm -v $(pwd):/share chef/inspec version
```

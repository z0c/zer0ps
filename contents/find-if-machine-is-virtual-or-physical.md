# Find if a machine is virtual or physical

In Centos

$ sudo facter 2> /dev/null | grep virtual

Sample output:

[Physical system]

is_virtual => false
virtual => physical

[Virtual system]

is_virtual => true
virtual => kvm

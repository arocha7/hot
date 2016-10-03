Basic Heat templates for AutoScaling
====================================


Eg. #1. deploy a simple stack to create a VM and attach to an existing Volume. 

NOTE: to create a new Volume, use Horizon dashboard or use CLI:
* $ nova help volume-attach
* $ nova volume-attach 'server' 'volume' 'device'

Eg. #2. deploy a simple stack to create a VM and a Volume to attach

Eg. #3. deploy an autoscale stack to apply 
  - stress a node (eg, $ cat /dev/zero > /dev/null )
  - verify Ceilometer metrics
  - confirm the instantiation of new nodes
  - stop the stress load on the node
  - confirm the stop of the instantiated nodes due to stress

ffs - deploy an AutoScale NLB with Floating IP


REQUIREMENTS

1. Obtain the 'openrc' file to connect to Openstack
 Openstack dashboard --> Compute tab --> Access and Security --> API Access --> Download Openstack RC file v2.0

2. Adapt customized parameters to your platform, eg: keypair, images, flavors

* $ nova keypair-list list
* $ openstack image list
* $ openstack flavor list


USAGE

* $ openstack stack create --template deploy-vm2sp4qi.yaml SON-SP4QI
* $ openstack stack list
* $ openstack stack show <stackID>
* $ openstack stack delete <stackID>


REFERENCES

- HOT guide: http://docs.openstack.org/developer/heat/template_guide/hot_guide.html
- HOT specs: http://docs.openstack.org/developer/heat/template_guide/hot_spec.html
- Repositories of Heat templates: https://github.com/openstack/heat-templates/
- DSL to be used with Heat: https://wiki.openstack.org/wiki/Heat/DSL


Basic Heat templates for AutoScaling

NOTE: adapt customized parameters to your platform, eg: keypair, images, flavors

1. deploy a simple stack to create a VM with an attached existing Volume
   a) create a Volume using Horizon dashboard or using CLI 
      $ nova help volume-attach
      usage: nova volume-attach <server> <volume> <device>

2. deploy a simple stack to create a VM and a Volume to attach

3. deploy an autoscale stack to apply 
   - stress a node (eg, $ cat /dev/zero > /dev/null )
   - verify Ceilometer metrics
   - confirm the instantiation of new nodes
   - stop the stress load on the node
   - confirm the stop of the instantiated nodes due to stress

ffs - deploy an AutoScale NLB with Floating IP

References:

- HOT guide: http://docs.openstack.org/developer/heat/template_guide/hot_guide.html
- HOT specs: http://docs.openstack.org/developer/heat/template_guide/hot_spec.html
- Repositories of Heat templates: https://github.com/openstack/heat-templates/
- DSL to be used with Heat: https://wiki.openstack.org/wiki/Heat/DSL

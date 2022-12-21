# rticonnextdds-dpse-examples

This repository includes examples on how to configure RTI Connext DDS Libraries,
Tools, and Services to communicate with RTI Connext Micro using DPSE (Dynamic
Participant/Static Endpoint) discovery.

RTI Connext Core Libraries, Tools, and Services using Limited Bandwidth Endpoint
Discovery Plugin have been tested against RTI Connext Micro using DPSE discovery.

For more information about DPSE discovery, please refer to the 
[RTI Connext Micro User's Manual](https://community.rti.com/static/documentation/connext-micro/2.4.14/doc/html/usersmanual/discovery.html#static-discovery-plugin).

For more information about the Limited Bandwidth Endpoint Discovery Plugin,
please refer to the [RTI Limited Bandwidth Plugins User's Manual](https://community.rti.com/static/documentation/connext-dds/6.1.2/doc/manuals/addon_products/limited_bandwidth_plugins/users_manual/index.htm)
and the [RTI Limited Bandwidth Plugins Installation Guide](https://community.rti.com/static/documentation/connext-dds/6.1.2/doc/manuals/addon_products/limited_bandwidth_plugins/installation_guide/index.htm).

All the examples use the type in the file HelloWorld.xml in this folder.

To contribute enhancements or additional examples to the repository, follow the
instructions on our [RTI Connext DDS Examples
Wiki](https://github.com/rticommunity/rticonnextdds-examples/wiki). Your
contributions will be reviewed and, as soon as they are approved, they will
automatically be included in the [RTI Community Portal Examples
Section](http://community.rti.com). See [CONTRIBUTING.md](https://github.com/rticommunity/rticonnextdds-dpse-examples/blob/master/CONTRIBUTING.md)
for further information about how to contribute with new examples to this repository.

The examples contained in the
[master](https://github.com/rticommunity/rticonnextdds-examples/tree/master) and
[develop](https://github.com/rticommunity/rticonnextdds-examples/tree/develop)
branches of this repository have been built and tested against RTI Connext DDS
6.1.2 and RTI Connext Micro 2.4.14. If you need examples that have been built
and tested against older versions of RTI Connext DDS, please check out the
appropriate branch or knowledge base:

- [release/6.1.0](https://github.com/rticommunity/rticonnextdds-dpse-examples/tree/release/6.1.0)
- [release/5.2.0](https://community.rti.com/kb/interoperability-connext-dds-micro-dpse-connext-dds-professional)

## Prerequisites

Before running these examples you need to install:

- RTI Connext Professional 6.1.2
- Limited Bandwidth Endpoint Discovery Plugin for Connext 6.1.2
- RTI Connext Micro 2.4.14

## About the examples

Each of the examples has a configuration file; for example, 
USER_ROUTING_SERVICE.xml is the configuration file for Routing Service. 
In these configuration files, the only allowed interface is 127.0.0.1 
(see XML tag "allow_interfaces_list"). This is needed to prevent 
resource exhaustion in RTI Connext Micro in case the OS where you 
run the example has too many network interfaces.

This configuration will work if you run the example with both the publisher
application and the subscriber application in the same OS. In case you want
to use different OSes to run the publisher and subscriber applications, you 
will need to add a new element in the tag with the interface name or IP 
address that you want to use.

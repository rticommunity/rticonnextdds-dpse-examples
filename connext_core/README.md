# Connext DDS Core Libraries

In this directory you will find an example that illustrates how to configure 
RTI Connext DDS Core Libraries to use the Limited Bandwidth Endpoint Discovery
Plugin.

For more information about the RTI Connext DDS Core Libraries, please refer to
the [RTI Connext DDS Core Libraries User's Manual](https://community.rti.com/static/documentation/connext-dds/6.1.0/doc/manuals/connext_dds_professional/users_manual/index.htm).

The file USER_QOS_PROFILES.xml contains the configuration needed for the
publisher application (see profile "LBEDiscoveryPluginExamplePublisher_Profile")
and the subscriber application (see profile "LBEDiscoveryPluginExampleSubscriber_Profile").
By default, the configuration only allows use of the loopback interface (127.0.0.1).
This is done to prevent resource exhaustion in Connext Micro applications.
You can update this with the interface name or IP address that you wish to use.

## How to Generate the Example and Compile

The first thing you need to do is to generate the type support files and the
makefiles needed for this example. You can do this by running rtiddsgen with
the following command:

```console
cd <this git repository>/connext_core

rtiddsgen -create typeFiles -create makefiles -platform <architecture> -language C++ ../HelloWorld.xml -d .
```

Your <architecture> is the combination of a processor, OS, and compiler version
that you will use to build your application. For example, when compiling with a 
x64 processor, 64-bit Windows, and Visual Studio 2015, your architecture is 
x64Win64VS2015. This should match one of the target architectures that you have 
installed.

Depending on the architecture, rtiddsgen generates a makefile, Visual Studio
solution file, etc. You can use this to compile the publisher and subscriber
applications.

You have to compile using shared libraries (not static libraries), such as
"Debug DLL" or "Release DLL", because the Limited Bandwith Endpoint Discovery
Plugin library is loaded dynamically. Therefore all RTI Connext DDS Core Libraries 
need to be loaded dynamically.

## How to Run

You can find the publisher and subscriber executables in the subfolder
"objs/<architecture>". For example, when compiling with VS2015, the 
path to the publisher is
"objs\x64Win64VS2015\HelloWorld_publisher.exe" and the subscriber is
"objs\x64Win64VS2015\HelloWorld_subscriber.exe"

As an example, you can run the publisher application with the following commands:

```console
cd <this git repository>/connext_core

objs\x64Win64VS2015\HelloWorld_publisher.exe -domain 58
```

and the subscriber application with the following commands:

```console
cd <this git repository>/connext_core

objs\x64Win64VS2015\HelloWorld_subscriber.exe -domain 58
```

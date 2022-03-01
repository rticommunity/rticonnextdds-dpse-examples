# Connext DDS Core Libraries

In this directory you will find an example that illustrates how to configure 
RTI Connext DDS Micro to use the DPSE discovery plugin.

For more information about RTI Connext DDS Micro, please refer to
the [RTI Connext DDS Micro User's Manual]
(https://community.rti.com/static/documentation/connext-micro/2.4.14/doc/html/introduction.html).

## How to Generate the Example and Compile

The first thing you need to do is to generate the type support files and the
makefiles needed for this example. You can do this by running rtiddsgen with
the following command:

```console
cd <this git repository>/connext_micro

rtiddsgen -example ../HelloWorld.xml -d . -language C
```

A README.txt file is generated with instructions on how to compile the publisher
and subscriber applications.

Note: rtiddsgen will show some warnings indicating that some files exist and
will not be overwritten. That is ok as we do not wish to replace all the example
files in this folder.

## How to Run

You can find the publisher and subscriber executables in the subfolder
"objs/<architecture/Debug|Release>". For example, when performing a debug build with VS2010,
the path to the publisher is "objs\i86Win32VS2010\Debug\HelloWorld_publisher.exe"
and the path to the subscriber is "objs\i86Win32VS2010\Debug\HelloWorld_subscriber.exe"

As an example you can run the publisher application with the following commands:

```console
cd <this git repository>/connext_micro

objs\i86Win32VS2010\Debug\HelloWorld_publisher.exe -domain 58 -udp_intf "Wi-Fi"  -peer 127.0.0.1
```

and the subscriber application with the following commands:

```console
cd <this git repository>/connext_micro

objs\i86Win32VS2010\Debug\HelloWorld_subscriber.exe -domain 58 -udp_intf "Wi-Fi"  -peer 127.0.0.1
```

In order to avoid resource exhaustion it is recommended to run the applications
using the optional parameter "-udp_intf". You should use the name of a network
interface in your system.

The peer "127.0.0.1" should be only valid if you run the publisher and subscriber
in the same OS.


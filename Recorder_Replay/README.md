# Recording and Replay Service

In this directory you will find an example that illustrates how to
configure RTI Recording and Replay to use the Limited Bandwidth Endpoint
Discovery Plugin and record and replay data sent and received by a:

 - Connext Micro application configured with DPSE discovery.
 - Connext Core application configured with the Limited Bandwidth Endpoint
   Discovery Plugin.

For more information about Recording Service, please refer to the [User's Manual](https://community.rti.com/static/documentation/connext-dds/6.1.0/doc/manuals/connext_dds_professional/services/recording_service/recorder/record_index.html).

For more information about Replay Service, please refer to the [User's Manual](https://community.rti.com/static/documentation/connext-dds/6.1.0/doc/manuals/connext_dds_professional/services/recording_service/replay/replay_index.html).

## Run the Publisher Application and Subscriber Applications.

You can use the publisher and subscriber based on RTI Connext Micro and you
can find it in folder "connext_micro" or the publisher based on RTI Connext
Core libraries and you can find it in folder "connext_core". See the 
documentation in these folders to know how to compile and run the applications.

## How to Run Recording Service

In the RTI Connext Launcher, in the tab with name "Services", click the icon with
the name "Recording Service" and you will see the following window:

![recorder](img/recorder.jpg)

Before running Recording Service you need to perform the following actions:

- Click button with name "..." to select the working directory and select 
  this directory.
- Because a file with name USER_RECORDING_SERVICE.xml is found in this directory
  the user configuration will automatically update to file
  "<this git repository>/Recording_Replay/USER_RECORDING_SERVICE.xml".
- Select the configuration with name "recorderDPSE - from USER"

Once you click the "Run" button Recording Service will be executed in a new window
and it will start recording all information published by the publisher application.

Alternatively you can also run Recording Service using the same configuration as
the previous example with the following commands:

```console
cd <this git repository>/Recorder_Replay

rtirecordingservice.bat -cfgName recorderDPSE 
```

As configured in file USER_RECORDING_SERVICE.xml will record data in subdirectory
"cdr_recording".

You can record some data and stop the publisher application and Recording Service
after some time.

## How to Run Recording Service

In the RTI Connext Launcher, in the tab with name "Services", click the icon with
the name "Replay Service" and you will see the following window:

![spy](img/replay.jpg)

Before running Replay Service you need to perform the following actions:

- Click button with name "..." to select the working directory and select 
  this directory.
- Because a file with name USER_REPLAY_SERVICE.xml is found in this directory
  the user configuration will automatically update to file
  "<this git repository>/Recording_Replay/USER_REPLAY_SERVICE.xml".
- Select the configuration with name "replayDPSE - from USER"

Once you click the "Run" button Replay Service will be executed in a new window
and it will start playing all information previously recorded by Recording Service.
The subscriber application will receive that information.

Alternatively you can also run Replay Service using the same configuration as
the previous example with the following commands:

```console
cd <this git repository>/Recorder_Replay

rtireplayservice.bat -cfgName replayDPSE
```
![Logo](admin/knx.png)
# ioBroker.knx
=================

[![NPM version](http://img.shields.io/npm/v/iobroker.knx.svg)](https://www.npmjs.com/package/iobroker.knx)
[![Downloads](https://img.shields.io/npm/dm/iobroker.knx.svg)](https://www.npmjs.com/package/iobroker.knx)

[![NPM](https://nodei.co/npm/iobroker.knx.png?downloads=true)](https://nodei.co/npm/iobroker.knx/)


*** The adapter is only compatible with Node 4.x and higher!! ***

This adapter allows importing of knxproj Files from ETS. It generates the translation between KNX- groupaddresses and ioBroker and put the devices into rooms (esp. for MobileUI).

It connects to standard KNX/LAN Gateways.

Befor beginning: Every DPT of com.Objects should be set in your ETS project. Every device should be sortet into your facility structure.

# Adapterconfiguration
After installing this adapter, open the adapter configuration. Fill in:
##### KNX Gateway IP
<IP of your KNX/Lan GW> with ipv4 format

##### Port
this is normally port 3671

##### phys. EIB Adress
fill in free phys. address corresponding to your KNX-architecture

##### Upload knxproj
here you can upload your ETS Export in "knxproj" format.
###### !!! I'm sorry, but at the moment, there is no user feedback while processing the file (it can take up to a minute) !!!
After successful import a message shows how much objects where recognized.

Hit "save & close" and the adapter should start.
While starting the adapter reads all groupAdresses with read-Flag. This could take a while and can produce a high load on your KNX-bus. But the values in your visare updatet after start.

## Objects
Here is under knx.0 the group adress tree like in your ETS project.

## Enumerations
If you have a Buildingstructure in your ETS with the corresponding devices, it will be shown here. Under "members" are the names of groupaddresses listet from the devices with send-Flag in this Group.

#Usage
If the adapter startet successfully your datapoints will be available for everything you like to do.
Try out "mobileUI".

## Datapoint Types
At the moment are DPT1 - DPT20 with subtypes and DPT238 available. But not all are validated.


# Known Problems
- many Datapointtypes are missing ( takes time to implement )
- does not work with babtec (means it does not work with babtec as KNX/LAN gateway)


## Changelog
### 0.8.1 (2017-02-06)
* fixed DPT1 switch problem

### 0.8.0 (2017-02-xx) comming soon

### 0.7.3 (2016-12-22)
* (chefkoch009) more DPT's are supported
* faster Startup
* implemented generation of room list with device dependicies

### 0.7.2 (2016-11-20)
* (chefkoch009) added necessary dependicies

### 0.7.1 (2016-11-19)
* (chefkoch009) Support standard KNX/LAN Gateways.

### 0.7.0 (2016-10-13)
* (chefkoch009) Support of project export

### 0.6.0 (2016-07-20)
* (chefkoch009) redesign

### 0.5.0
  (vegetto) include vis widget

#### 0.4.0
* (bluefox) fix errors with grunt

#### 0.2.0
* (bluefox) initial release

## License
The CC-NC-BY License (CC-NC-BY)

Copyright (c) 2016 K.Ringmann <info@punktnetzwerk.net>

THE WORK IS PROVIDED UNDER THE TERMS OF THIS CREATIVE
COMMONS PUBLIC LICENSE ("CCPL" OR "LICENSE"). THE WORK IS PROTECTED BY
COPYRIGHT AND/OR OTHER APPLICABLE LAW. ANY USE OF THE WORK OTHER THAN AS
AUTHORIZED UNDER THIS LICENSE OR COPYRIGHT LAW IS PROHIBITED.

BY EXERCISING ANY RIGHTS TO THE WORK PROVIDED HERE, YOU ACCEPT AND AGREE
TO BE BOUND BY THE TERMS OF THIS LICENSE. TO THE EXTENT THIS LICENSE MAY
BE CONSIDERED TO BE A CONTRACT, THE LICENSOR GRANTS YOU THE RIGHTS
CONTAINED HERE IN CONSIDERATION OF YOUR ACCEPTANCE OF SUCH TERMS AND
CONDITIONS.

Read full license text in [LICENSE](LICENSE)

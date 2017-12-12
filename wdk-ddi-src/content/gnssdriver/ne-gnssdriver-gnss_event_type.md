---
UID: NE.gnssdriver.GNSS_EVENT_TYPE
title: GNSS_EVENT_TYPE
author: windows-driver-content
description: This enumeration indicates the type of an event and is used by the GNSS_EVENT structure.
old-location: sensors\gnss_event_type.htm
old-project: sensors
ms.assetid: BC862E22-992E-497D-B370-97ABE8897728
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: GNSS_EVENT_TYPE, GNSS_EVENT_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: gnssdriver.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GNSS_EVENT_TYPE
req.alt-loc: gnssdriver.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
---

# GNSS_EVENT_TYPE enumeration



## -description
This enumeration indicates the type of an event and is used by the <a href="sensors.gnss_event">GNSS_EVENT</a> structure.

The GNSS driver utilizes events to send solicited and unsolicited information to the GNSS adapter. Events can occur for various reasons, such as a driver request to the GNSS adapter for the injection of assistance data or for informational purposes.




## -syntax

````
typedef enum  { 
  GNSS_Event_FixAvailable             = 0x0001,
  GNSS_Event_RequireAgnss             = 0x0002,
  GNSS_Event_Error                    = 0x0003,
  GNSS_Event_NiRequest                = 0x000C,
  GNSS_Event_NmeaData                 = 0x000D,
  GNSS_Event_GeofenceAlertData        = 0x000E,
  GNSS_Event_GeofencesTrackingStatus  = 0x000F,
  GNSS_Event_DriverRequest            = 0x0010,
  GNSS_Event_BreadcrumbAlertEvent     = 0x0011,
  GNSS_Event_Custom                   = 0x8000
} GNSS_EVENT_TYPE;
````


## -enum-fields

### -field GNSS_Event_FixAvailable

This event is raised as a result of a prior <a href="..\gnssdriver\ni-gnssdriver-ioctl_gnss_get_fixdata.md">IOCTL_GNSS_GET_FIXDATA</a> call from the adapter. The GNSS driver raises this event when a fix is available for the adapter to collect. The fix data is included in the event data in form of <a href="sensors.gnss_fixdata">GNSS_FIXDATA</a> structure.


### -field GNSS_Event_RequireAgnss

This event is raised as a result of a prior <a href="..\gnssdriver\ni-gnssdriver-ioctl_gnss_listen_agnss.md">IOCTL_GNSS_LISTEN_AGNSS</a> call from the adapter. The driver raises this event whenever it needs injection of certain AGNSS assistance data. The specifics of the injection are available in the event data in form of <a href="sensors.gnss_agnss_request_param">GNSS_AGNSS_REQUEST_PARAM</a> structure.


### -field GNSS_Event_Error

This event is raised as a result of a prior <a href="..\gnssdriver\ni-gnssdriver-ioctl_gnss_listen_error.md">IOCTL_GNSS_LISTEN_ERROR</a> call from the adapter. The driver raises this event when an out-of-band error occurs that the adapter needs to be aware of. The error details are available in the event data in form of <a href="sensors.gnss_errorinfo">GNSS_ERRORINFO</a> structure. The information can be used by Microsoft to capture telemetry data about what type of errors are seen in the field by different devices, and the data could be shared with OEMs/IHVs to help understand common issues and increase the quality of GNSS engine implementations.


### -field GNSS_Event_NiRequest

This event is raised when the driver wants to notify an NI request. The HLOS will process the request (for example, display a dialog if requested) then inject a response back to the driver.


### -field GNSS_Event_NmeaData

This event is raised as a result of a prior <a href="..\gnssdriver\ni-gnssdriver-ioctl_gnss_listen_nmea.md">IOCTL_GNSS_LISTEN_NMEA</a> call, if NMEA logging is enabled in the device. The GNSS driver raises this event when NMEA data is ready to be read by the calling client. The calling client will typically be a test tool. The NMEA sentences data is included in the event data in form of <a href="sensors.gnss_nmea_data">GNSS_NMEA_DATA</a> structure.



### -field GNSS_Event_GeofenceAlertData

A previously created geofence has been breached. At the creation time of the geofence, the HLOS had specifically asked for an alert when such a breach happens. For example, an alert for entry should not be raised if the HLOS has requested only exit alerts.


### -field GNSS_Event_GeofencesTrackingStatus

The GNSS engine is unable to track one or more geofences due to bad signal conditions or other positioning issues. A status is also raised when the GNSS engine has recovered from a previous failure condition and is now able to track all the geofences.


### -field GNSS_Event_DriverRequest

Reserved for future extension. The GNSS driver is requesting some out-of-band information from the HLOS.


### -field GNSS_Event_BreadcrumbAlertEvent

Reserved for future extension:

<table>
<tr>
<td>
0x0012- 0x7FFF

</td>
<td>
For each new event type, there will be a well-defined IOCTL describing the initiation process of this event by the adapter, and a well-defined event data structure describing the data/command associated with this event.

</td>
</tr>
</table>
 


### -field GNSS_Event_Custom

Reserved for vendor-specific custom actions:

<table>
<tr>
<td>
0x8000-0xFFFF

</td>
<td>
The GNSS driver raises this event as needed. The command and data are packaged in an opaque blob as part of the event data. The package is sent up to the adapter for marshaling to the GNSS helper component.

</td>
</tr>
</table>
 


## -remarks
Events can be of various types. Certain events occur as a result of a previous request initiated by the driver, for example, start fix request. Certain events are raised for informational purpose. Assistance events are raised when the driver requires the adapter to inject specific assistance data.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Gnssdriver.h</dt>
</dl>
</td>
</tr>
</table>
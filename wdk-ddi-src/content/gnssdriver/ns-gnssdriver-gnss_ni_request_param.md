---
UID: NS:gnssdriver.GNSS_NI_REQUEST_PARAM
title: GNSS_NI_REQUEST_PARAM
author: windows-driver-content
description: This structure contains the NI request parameters.
old-location: sensors\gnss_ni_request_param.htm
old-project: sensors
ms.assetid: 0528EEE6-31D6-4CF6-8192-3557C28B4D10
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: sensors.gnss_ni_request_param, GNSS_NI_REQUEST_PARAM, gnssdriver/PGNSS_NI_REQUEST_PARAM, GNSS_NI_REQUEST_PARAM structure [Sensor Devices], gnssdriver/GNSS_NI_REQUEST_PARAM, PGNSS_NI_REQUEST_PARAM, PGNSS_NI_REQUEST_PARAM structure pointer [Sensor Devices], *PGNSS_NI_REQUEST_PARAM
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: gnssdriver.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	gnssdriver.h
apiname:
-	GNSS_NI_REQUEST_PARAM
product: Windows
targetos: Windows
req.typenames: "*PGNSS_NI_REQUEST_PARAM, GNSS_NI_REQUEST_PARAM"
---

# GNSS_NI_REQUEST_PARAM structure
This structure contains the NI request parameters.

## Syntax
````
typedef struct {
  ULONG                     Size;
  ULONG                     Version;
  ULONG                     RequestId;
  GNSS_NI_REQUEST_TYPE      RequestType;
  GNSS_NI_NOTIFICATION_TYPE NotificationType;
  GNSS_NI_PLANE_TYPE        RequestPlaneType;
  union {
    GNSS_SUPL_NI_INFO  SuplNiInfo;
    GNSS_CP_NI_INFO    CpNiInfo;
    GNSS_V2UPL_NI_INFO V2UplNiInfo;
  };
  ULONG                     ResponseTimeInSec;
  ULONG                     EmergencyLocation;
} GNSS_NI_REQUEST_PARAM, *PGNSS_NI_REQUEST_PARAM;
````

## Members


`EmergencyLocation`

Indicates an emergency request, so an existing NI dialog will be dismissed and the new request will be processed immediately.

`NotificationType`

A <a href="..\gnssdriver\ne-gnssdriver-gnss_ni_notification_type.md">GNSS_NI_NOTIFICATION_TYPE</a> enumeration value that specifies the notification type.

`RequestId`

The ID that uniquely identifies the NI request. It is used later by the NI response to identify the request to respond to.

`RequestPlaneType`

A <a href="..\gnssdriver\ne-gnssdriver-gnss_ni_plane_type.md">GNSS_NI_PLANE_TYPE</a> enumeration value that specifies the plane type.

`RequestType`

A <a href="..\gnssdriver\ne-gnssdriver-gnss_ni_request_type.md">GNSS_NI_REQUEST_TYPE</a> enumeration value that specifies the request type.

`ResponseTimeInSec`

The required response time, in seconds.

`Size`

Structure size.

`Version`

Version number.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | gnssdriver.h |
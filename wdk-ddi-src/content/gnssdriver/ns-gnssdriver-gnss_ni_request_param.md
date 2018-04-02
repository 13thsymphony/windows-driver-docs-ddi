---
UID: NS:gnssdriver.GNSS_NI_REQUEST_PARAM
title: GNSS_NI_REQUEST_PARAM
author: windows-driver-content
description: This structure contains the NI request parameters.
old-location: sensors\gnss_ni_request_param.htm
old-project: sensors
ms.assetid: 0528EEE6-31D6-4CF6-8192-3557C28B4D10
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: "*PGNSS_NI_REQUEST_PARAM, GNSS_NI_REQUEST_PARAM, GNSS_NI_REQUEST_PARAM structure [Sensor Devices], PGNSS_NI_REQUEST_PARAM, PGNSS_NI_REQUEST_PARAM structure pointer [Sensor Devices], gnssdriver/GNSS_NI_REQUEST_PARAM, gnssdriver/PGNSS_NI_REQUEST_PARAM, sensors.gnss_ni_request_param"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	gnssdriver.h
api_name:
-	GNSS_NI_REQUEST_PARAM
product:
- Windows
targetos: Windows
req.typenames: GNSS_NI_REQUEST_PARAM, *PGNSS_NI_REQUEST_PARAM
---

# GNSS_NI_REQUEST_PARAM structure
This structure contains the NI request parameters.

## Syntax
```
typedef struct GNSS_NI_REQUEST_PARAM {
  ULONG                     Size;
  ULONG                     Version;
  ULONG                     RequestId;
  GNSS_NI_REQUEST_TYPE      RequestType;
  GNSS_NI_NOTIFICATION_TYPE NotificationType;
  GNSS_NI_PLANE_TYPE        RequestPlaneType;
  union {
    GNSS_CP_NI_INFO    CpNiInfo;
    GNSS_SUPL_NI_INFO  SuplNiInfo;
    GNSS_V2UPL_NI_INFO V2UplNiInfo;
  };
  ULONG                     ResponseTimeInSec;
  BOOL                      EmergencyLocation;
}  *PGNSS_NI_REQUEST_PARAM;
```

## Members


`Size`

Structure size.

`Version`

Version number.

`RequestId`

The ID that uniquely identifies the NI request. It is used later by the NI response to identify the request to respond to.

`RequestType`

A <a href="https://msdn.microsoft.com/library/windows/hardware/dn925194">GNSS_NI_REQUEST_TYPE</a> enumeration value that specifies the request type.

`NotificationType`

A <a href="https://msdn.microsoft.com/library/windows/hardware/dn925185">GNSS_NI_NOTIFICATION_TYPE</a> enumeration value that specifies the notification type.

`RequestPlaneType`

A <a href="https://msdn.microsoft.com/library/windows/hardware/dn925188">GNSS_NI_PLANE_TYPE</a> enumeration value that specifies the plane type.

`ResponseTimeInSec`

The required response time, in seconds.

`EmergencyLocation`

Indicates an emergency request, so an existing NI dialog will be dismissed and the new request will be processed immediately.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | gnssdriver.h |
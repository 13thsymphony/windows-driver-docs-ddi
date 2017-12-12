---
UID: NE.gnssdriver.GNSS_NI_PLANE_TYPE
title: GNSS_NI_PLANE_TYPE
author: windows-driver-content
description: This enumeration indicates the plane type of a network initiated (NI) request represented by the GNSS_NI_REQUEST_PARAM structure.
old-location: sensors\gnss_ni_plane_type.htm
old-project: sensors
ms.assetid: F06FFABA-D7AB-4301-9F73-CE4BBB0B8AA6
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: GNSS_NI_PLANE_TYPE, GNSS_NI_PLANE_TYPE
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
req.alt-api: GNSS_NI_PLANE_TYPE
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

# GNSS_NI_PLANE_TYPE enumeration



## -description
This enumeration indicates the plane type of a network initiated (NI) request represented by the <a href="sensors.gnss_ni_request_param">GNSS_NI_REQUEST_PARAM</a> structure.



## -syntax

````
typedef enum  { 
  GNSS_NI_SUPL   = 0x01,
  GNSS_NI_CP     = 0x02,
  GNSS_NI_V2UPL  = 0x03
} GNSS_NI_PLANE_TYPE;
````


## -enum-fields

### -field GNSS_NI_SUPL

Indicates the plane type of the request is SUPL.


### -field GNSS_NI_CP

Indicates the plane type of the request is CP.


### -field GNSS_NI_V2UPL

Indicates plane type of the request is V2UPL.


## -remarks


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
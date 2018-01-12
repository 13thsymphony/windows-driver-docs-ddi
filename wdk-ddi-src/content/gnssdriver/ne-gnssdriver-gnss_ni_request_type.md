---
UID: NE:gnssdriver.GNSS_NI_REQUEST_TYPE
title: GNSS_NI_REQUEST_TYPE
author: windows-driver-content
description: This enumeration indicates the network initiated (NI) request type represented by the GNSS_NI_REQUEST_PARAM structure.
old-location: sensors\gnss_ni_request_type.htm
old-project: sensors
ms.assetid: 79AFC7D8-5A51-49CC-8ADA-7D21C6859254
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GNSS_NI_REQUEST_TYPE, GNSS_NI_REQUEST_TYPE
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
req.alt-api: GNSS_NI_REQUEST_TYPE
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
req.typenames: GNSS_NI_REQUEST_TYPE
---

# GNSS_NI_REQUEST_TYPE enumeration



## -description
This enumeration indicates the network initiated (NI) request type represented by the <a href="..\gnssdriver\ns-gnssdriver-gnss_ni_request_param.md">GNSS_NI_REQUEST_PARAM</a> structure.



## -syntax

````
typedef enum  { 
  GNSS_NI_Request_SingleShot   = 0x01,
  GNSS_NI_Request_AreaTrigger  = 0x02
} GNSS_NI_REQUEST_TYPE;
````


## -enum-fields

### -field GNSS_NI_Request_SingleShot

Indicates the request type is single shot.


### -field GNSS_NI_Request_AreaTrigger

Indicates the request type is tracking.


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
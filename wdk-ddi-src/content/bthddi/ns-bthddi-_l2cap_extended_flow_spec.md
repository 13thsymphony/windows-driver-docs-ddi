---
UID: NS:bthddi._L2CAP_EXTENDED_FLOW_SPEC
title: _L2CAP_EXTENDED_FLOW_SPEC
author: windows-driver-content
description: The L2CAP_EXTENDED_FLOW_SPEC is reserved for future use.
old-location: bltooth\l2cap_extended_flow_spec.htm
old-project: bltooth
ms.assetid: B190484F-1A87-4C52-A1FF-4D4EB593A963
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: _L2CAP_EXTENDED_FLOW_SPEC, L2CAP_EXTENDED_FLOW_SPEC, *PL2CAP_EXTENDED_FLOW_SPEC
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Windows
req.target-min-winverclnt: Versions: Supported in Windows 8 and later versions of Windows
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: L2CAP_EXTENDED_FLOW_SPEC
req.alt-loc: Bthddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Developers should code this function to operate at either IRQL = DISPATCH_LEVEL (if the callback   function does not access paged memory), or IRQL = PASSIVE_LEVEL (if the callback function must access   paged memory)
req.typenames: L2CAP_EXTENDED_FLOW_SPEC, *PL2CAP_EXTENDED_FLOW_SPEC
---

# _L2CAP_EXTENDED_FLOW_SPEC structure



## -description
The L2CAP_EXTENDED_FLOW_SPEC is reserved for future use.



## -syntax

````
typedef struct _L2CAP_EXTENDED_FLOW_SPEC {
  UCHAR  Identifier;
  UCHAR  ServiceType;
  USHORT MaxSDUSize;
  ULONG  SDUInterArrivalTime;
  ULONG  AccessLatency;
  ULONG  FlushTimeout;
} L2CAP_EXTENDED_FLOW_SPEC, *PL2CAP_EXTENDED_FLOW_SPEC;
````


## -struct-fields

### -field Identifier

Reserved. Do not use.


### -field ServiceType

Reserved. Do not use.


### -field MaxSDUSize

Reserved. Do not use.


### -field SDUInterArrivalTime

Reserved. Do not use.


### -field AccessLatency

Reserved. Do not use.


### -field FlushTimeout

Reserved. Do not use.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Versions: Supported in Windows 8 and later versions of Windows

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Bthddi.h (include Bthddi.h)</dt>
</dl>
</td>
</tr>
</table>
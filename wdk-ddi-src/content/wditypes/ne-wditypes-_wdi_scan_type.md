---
UID: NE.wditypes._WDI_SCAN_TYPE
title: _WDI_SCAN_TYPE
author: windows-driver-content
description: The WDI_SCAN_TYPE enumeration defines the scan types.
old-location: netvista\wdi_scan_type.htm
old-project: NetVista
ms.assetid: DF4ECD03-2C2F-44B3-82BE-E57B333AF069
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _WDI_SCAN_TYPE, WDI_SCAN_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wditypes.hpp
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WDI_SCAN_TYPE
req.alt-loc: wditypes.hpp
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
req.product: Windows 10 or later.
---

# _WDI_SCAN_TYPE enumeration



## -description
The WDI_SCAN_TYPE enumeration defines the scan types.



## -syntax

````
typedef enum _WDI_SCAN_TYPE { 
  WDI_SCAN_TYPE_ACTIVE_ONLY   = 1,
  WDI_SCAN_TYPE_PASSIVE_ONLY  = 2,
  WDI_SCAN_TYPE_AUTO          = 3
} WDI_SCAN_TYPE;
````


## -enum-fields

### -field WDI_SCAN_TYPE_ACTIVE_ONLY

The port should transmit a probe request on the channels that it scans. Even for active scans, the port must follow regulatory restrictions on the channel and must not scan on channels that would need a passive scan.


### -field WDI_SCAN_TYPE_PASSIVE_ONLY

The port should not transmit a probe request on the channels that it scans.


### -field WDI_SCAN_TYPE_AUTO

The port can perform an active or passive can or can use a combination of both scan types. It should prefer using Active scans when possible. This is the default scan type setting.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wditypes.hpp</dt>
</dl>
</td>
</tr>
</table>
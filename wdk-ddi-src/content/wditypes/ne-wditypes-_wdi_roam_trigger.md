---
UID: NE.wditypes._WDI_ROAM_TRIGGER
title: _WDI_ROAM_TRIGGER
author: windows-driver-content
description: The WDI_ROAM_TRIGGER enumeration defines roam triggers.
old-location: netvista\wdi_roam_trigger.htm
old-project: NetVista
ms.assetid: 7AFA084B-5EFC-429B-B6D1-F4E484B16921
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _WDI_ROAM_TRIGGER, WDI_ROAM_TRIGGER
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
req.alt-api: WDI_ROAM_TRIGGER
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

# _WDI_ROAM_TRIGGER enumeration



## -description
The WDI_ROAM_TRIGGER enumeration defines roam triggers.



## -syntax

````
typedef enum _WDI_ROAM_TRIGGER { 
  WDI_ROAM_TRIGGER_OTHER                            = 0x00000000,
  WDI_ROAM_TRIGGER_CRITICAL_BSS_TRANSITION_REQUEST  = 0x00000001
} WDI_ROAM_TRIGGER;
````


## -enum-fields

### -field WDI_ROAM_TRIGGER_OTHER

None.


### -field WDI_ROAM_TRIGGER_CRITICAL_BSS_TRANSITION_REQUEST

This value is for roams due to a BSS Transition Request by the AP with the Disassociation Imminent bit set.


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
---
UID: NE.wditypes._WDI_BSS_SELECTION_FLAGS
title: _WDI_BSS_SELECTION_FLAGS
author: windows-driver-content
description: The WDI_BSS_SELECTION_FLAGS enumeration defines flags for BSS selection.
old-location: netvista\wdi_bss_selection_flags.htm
old-project: NetVista
ms.assetid: 9C2F862B-8BA8-4947-9C3D-538715C99F26
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _WDI_BSS_SELECTION_FLAGS, WDI_BSS_SELECTION_FLAGS
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
req.alt-api: WDI_BSS_SELECTION_FLAGS
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

# _WDI_BSS_SELECTION_FLAGS enumeration



## -description
The WDI_BSS_SELECTION_FLAGS enumeration defines flags for BSS selection.



## -syntax

````
typedef enum _WDI_BSS_SELECTION_FLAGS { 
  WDI_BSS_SELECTION_HOST_PREFERRED                 = 0x00000001,
  WDI_BSS_SELECTION_RECENT_ASSOCIATION_ERROR       = 0x00000002,
  WDI_BSS_SELECTION_FLAGS_AP_REQUESTED_TRANSITION  = 0x00000004
} WDI_BSS_SELECTION_FLAGS;
````


## -enum-fields

### -field WDI_BSS_SELECTION_HOST_PREFERRED

Set for BSS entries that the host prefers to connect to. Non-preferred BSS entries would also be provided to the port, but should only be used  for connection if port performs its own BSS ranking.


### -field WDI_BSS_SELECTION_RECENT_ASSOCIATION_ERROR

Set for BSS entries that had recent association failures or were recently disassociated from. This flag is already accounted for by the host when setting WDI_BSS_SELECTION_HOST_PREFERRED.


### -field WDI_BSS_SELECTION_FLAGS_AP_REQUESTED_TRANSITION

Specifies whether this roam was requested by the AP or not (11v BSS Transition management request).


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
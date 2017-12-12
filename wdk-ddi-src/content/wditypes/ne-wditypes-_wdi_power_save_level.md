---
UID: NE.wditypes._WDI_POWER_SAVE_LEVEL
title: _WDI_POWER_SAVE_LEVEL
author: windows-driver-content
description: The WDI_POWER_SAVE_LEVEL enumeration defines the power save levels.
old-location: netvista\wdi_power_save_level.htm
old-project: netvista
ms.assetid: 3CB311C1-8FAE-44D5-896D-972F5DF1E88A
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _WDI_POWER_SAVE_LEVEL, WDI_POWER_SAVE_LEVEL
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
req.alt-api: WDI_POWER_SAVE_LEVEL
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

# _WDI_POWER_SAVE_LEVEL enumeration



## -description
The WDI_POWER_SAVE_LEVEL enumeration defines the power save levels.



## -syntax

````
typedef enum _WDI_POWER_SAVE_LEVEL { 
  WDI_POWER_SAVE_LEVEL_NO_POWER_SAVE  = 0,
  WDI_POWER_SAVE_LEVEL_FAST_PSP       = 8,
  WDI_POWER_SAVE_LEVEL_MAX_PSP        = 16,
  WDI_POWER_SAVE_LEVEL_MAXIMUM_LEVEL  = 24
} WDI_POWER_SAVE_LEVEL;
````


## -enum-fields

### -field WDI_POWER_SAVE_LEVEL_NO_POWER_SAVE

No power saving.


### -field WDI_POWER_SAVE_LEVEL_FAST_PSP

Fast PSP.


### -field WDI_POWER_SAVE_LEVEL_MAX_PSP

Maximum PSP.


### -field WDI_POWER_SAVE_LEVEL_MAXIMUM_LEVEL

Maximum power saving level.


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
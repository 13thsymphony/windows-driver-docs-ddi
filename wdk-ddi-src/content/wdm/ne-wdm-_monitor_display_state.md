---
UID: NE.wdm._MONITOR_DISPLAY_STATE
title: _MONITOR_DISPLAY_STATE
author: windows-driver-content
description: Indicates the power state of the monitor being displayed on.
old-location: kernel\monitor_display_state.htm
old-project: kernel
ms.assetid: 50F5C1AD-BA51-4376-8093-E8596265FDAF
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: _MONITOR_DISPLAY_STATE, *PMONITOR_DISPLAY_STATE, MONITOR_DISPLAY_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MONITOR_DISPLAY_STATE
req.alt-loc: wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# _MONITOR_DISPLAY_STATE enumeration



## -description
Indicates the power state of the monitor being displayed on.



## -syntax

````
typedef enum _MONITOR_DISPLAY_STATE { 
  PowerMonitorOff  = 0,
  PowerMonitorOn,
  PowerMonitorDim
} MONITOR_DISPLAY_STATE;
````


## -enum-fields

### -field PowerMonitorOff

This indicates that the monitor is off.


### -field PowerMonitorOn

This indicates that the monitor is on.


### -field PowerMonitorDim

This indicates that the monitor is dim.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h</dt>
</dl>
</td>
</tr>
</table>
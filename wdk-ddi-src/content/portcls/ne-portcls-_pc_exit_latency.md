---
UID: NE.portcls._PC_EXIT_LATENCY
title: _PC_EXIT_LATENCY
author: windows-driver-content
description: This topic discusses the PC_EXIT_LATENCY enum, and describes its members. The latency times map to specific maximum times in which the device must be able to exit its sleep state and enter the fully functional state (D0).
old-location: audio\pc_exit_latency.htm
old-project: audio
ms.assetid: 9D1DA7D6-4200-4B5A-9EA5-0455DF56D6D8
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _PC_EXIT_LATENCY, PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: portcls.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PC_EXIT_LATENCY
req.alt-loc: Portcls.h
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
---

# _PC_EXIT_LATENCY enumeration



## -description
This topic discusses the PC_EXIT_LATENCY enum, and describes its members. The latency times map to specific maximum times in which the device must be able to exit its sleep state and enter the fully functional state (D0).



## -syntax

````
typedef enum _PC_EXIT_LATENCY { 
  PcExitLatencyInstant     = 0,
  PcExitLatencyFast,
  PcExitLatencyResponsive
} PC_EXIT_LATENCY;
````


## -enum-fields

### -field PcExitLatencyInstant

Indicates a 0-millisecond latency. This means "Do not power down" and it  will only be sent when a device is in the D0 state.


### -field PcExitLatencyFast

Indicates a 35-millisecond resume latency.


### -field PcExitLatencyResponsive

Indicates a 300-millisecond resume latency.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Portcls.h</dt>
</dl>
</td>
</tr>
</table>
---
UID: NS:ntddk._POWER_THROTTLING_THREAD_STATE
title: _POWER_THROTTLING_THREAD_STATE
author: windows-driver-content
description: Stores the throttling policies and how to apply them to a target thread when that thread is subject to power management.
old-location: kernel\power_throttling_thread_state.htm
old-project: kernel
ms.assetid: 85659694-f93a-42dc-9fa4-f6fea6ad71d0
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _POWER_THROTTLING_THREAD_STATE, *PPOWER_THROTTLING_THREAD_STATE, POWER_THROTTLING_THREAD_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: POWER_THROTTLING_THREAD_STATE
req.alt-loc: Ntddk.h
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
req.typenames: *PPOWER_THROTTLING_THREAD_STATE, POWER_THROTTLING_THREAD_STATE
---

# _POWER_THROTTLING_THREAD_STATE structure



## -description
Stores the throttling policies and how to apply them to a target thread when that thread is subject to power management.



## -syntax

````
typedef struct _POWER_THROTTLING_THREAD_STATE {
  ULONG  Version;
  ULONG  ControlMask;
  ULONG  StateMask;
} POWER_THROTTLING_THREAD_STATE, POWER_THROTTLING_THREAD_STATE;
````


## -struct-fields

### -field Version

The version of this structure. Set to THREAD_POWER_THROTTLING_CURRENT_VERSION.


### -field ControlMask

Flags that enable the caller to take control of the power throttling mechanism.

<ul>
<li>THREAD_POWER_THROTTLING_EXECUTION_SPEED: Manages the execution speed of the process.</li>
</ul>

### -field StateMask

Flags that manage the power throttling mechanism on/off state.

<ul>
<li>THREAD_POWER_THROTTLING_EXECUTION_SPEED: Manages the execution speed of the process.</li>
</ul>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10, version 1709

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
<dt>Ntddk.h</dt>
</dl>
</td>
</tr>
</table>
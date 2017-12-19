---
UID: NF.ntddk.PsRegisterSiloMonitor
title: PsRegisterSiloMonitor function
author: windows-driver-content
description: This routine registers a server silo monitor that can receive notifications about server silo events.
old-location: kernel\psregistersilomonitor.htm
old-project: kernel
ms.assetid: C04F29FF-972C-44CC-8557-28C23827ADF0
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: PsRegisterSiloMonitor
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PsRegisterSiloMonitor
req.alt-loc: ntddk.h
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

# PsRegisterSiloMonitor function



## -description
This routine registers a server silo monitor that can receive notifications about server silo events.


<div class="alert"><b>Note</b>  To start receiving notifications, call the <a href="kernel.psstartsilomonitor">PsStartSiloMonitor</a> routine.</div>
<div> </div>




## -syntax

````
NTSTATUS PsRegisterSiloMonitor(
  _In_  PSILO_MONITOR_REGISTRATION Registration,
  _Out_ PSILO_MONITOR              *ReturnedMonitor
);
````


## -parameters

### -param Registration [in]

Specifies the server silo monitor to be registered, of type <a href="kernel.silo_monitor_registration">SILO_MONITOR_REGISTRATION</a>. 


### -param ReturnedMonitor [out]

Receives a pointer to the monitor. This pointer is used to make further monitor-related calls.


## -returns
The following NT status codes are returned.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The version specified in <b>ntddk.h</b> does not match <b>SILO_MONITOR_REGISTRATION_VERSION</b>, the component name is not specified, or the terminate callback is not supplied.
<dl>
<dt><b>STATUS_PRIVILEDGE_NOT_HELD</b></dt>
</dl>The routine is called in a silo.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>There is no memory to register a silo monitor or there is no available silo slot.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The operation completed successfully.

 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10, version 1607

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
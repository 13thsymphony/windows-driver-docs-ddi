---
UID: NC.ntddk.SILO_MONITOR_CREATE_CALLBACK
title: SILO_MONITOR_CREATE_CALLBACK
author: windows-driver-content
description: This is callback is invoked when a new silo is created.
old-location: kernel\silo_monitor_create_callback.htm
old-project: kernel
ms.assetid: C26C5162-4BB0-401E-9AF5-AF1D2D8715F9
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _FILTER_INITIALIZATION_DATA, *PFILTER_INITIALIZATION_DATA, PFILTER_INITIALIZATION_DATA, FILTER_INITIALIZATION_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CreateCallback
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

# SILO_MONITOR_CREATE_CALLBACK callback



## -description
This is callback is invoked when a new silo is created.



## -prototype

````
SILO_MONITOR_CREATE_CALLBACK CreateCallback;

NTSTATUS CreateCallback(
  _In_ PESILO Silo
)
{ ... }
````


## -parameters

### -param Silo [in]

The silo that was created.


## -returns
The NT code returned by the operation.


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
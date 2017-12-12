---
UID: NF.ntddk.PsGetCurrentSilo
title: PsGetCurrentSilo function
author: windows-driver-content
description: This routine returns the current silo for the calling thread. First the thread is checked to see if it has been attached to a silo. If not, then the thread is checked to see if it is in a silo.
old-location: kernel\psgetcurrentsilo.htm
old-project: kernel
ms.assetid: 535D7611-8C86-44CF-964C-731882A3AF69
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: PsGetCurrentSilo
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
req.alt-api: PsGetCurrentSilo
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
req.irql: _IRQL_requires_max_(DISPATCH_LEVEL)
---

# PsGetCurrentSilo function



## -description
This routine returns the current silo for the calling thread.  First the thread is checked to see if it has been attached to a silo. If not, then the thread is checked to see if it is in a silo.



## -syntax

````
PESILO PsGetCurrentSilo(void);
````


## -parameters


## -returns
A pointer to the <b>ESILO</b> object.  This pointer is valid for the current thread, but must be referenced before transferring to another thread (for example, via a workitem).

A pointer to the <b>ESILO</b> object.  This pointer is valid for the current thread, but must be referenced before transferring to another thread (for example, via a workitem).

A pointer to the <b>ESILO</b> object.  This pointer is valid for the current thread, but must be referenced before transferring to another thread (for example, via a workitem).


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
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
_IRQL_requires_max_(DISPATCH_LEVEL)

</td>
</tr>
</table>
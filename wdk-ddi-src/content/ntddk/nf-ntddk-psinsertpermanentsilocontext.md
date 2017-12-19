---
UID: NF.ntddk.PsInsertPermanentSiloContext
title: PsInsertPermanentSiloContext function
author: windows-driver-content
description: This routine inserts an object in an empty slot in a Silo.
old-location: kernel\psinsertpermanentsilocontext.htm
old-project: kernel
ms.assetid: ADBAB25B-7646-4E0E-AFD8-18B87A293674
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: PsInsertPermanentSiloContext
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
req.alt-api: PsInsertPermanentSiloContext
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

# PsInsertPermanentSiloContext function



## -description
This routine inserts an object in an empty slot in a <i>Silo</i>.



## -syntax

````
NTSTATUS PsInsertPermanentSiloContext(
  _In_ PESILO Silo,
  _In_ ULONG  ContextSlot,
  _In_ PVOID  SiloContext
);
````


## -parameters

### -param Silo [in]

The silo in which the object is to be inserted. This parameter is required and it cannot be <b>NULL</b>. 


### -param ContextSlot [in]

The slot in which the object is to be inserted. A slot allocated by the <a href="kernel.psallocsilocontextslot">PsAllocSiloContextSlot</a> routine.


### -param SiloContext [in]

The object to be inserted, created by the <a href="kernel.pscreatesilocontext">PsCreateSiloContext</a> routine. The object must be created using the same silo as specified in the <i>Silo</i> parameter. This parameter is required and it cannot be <b>NULL</b>. 


## -returns
The following NT status codes are returned.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>There are no resources in the system to perform the insert. This is an error code. 
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>The slot is not empty. This is an error code.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The operation completed successfully.

 


## -remarks
A successful call to <b>PsInsertPermanentSiloContext</b> increments the reference count on <i>SiloContext</i>. If <b>PsInsertPermanentSiloContext</b> fails, the reference count remains unchanged. In either case, after the routine completes, the caller must call <a href="kernel.psdereferencesilocontext">PsDereferenceSiloContext</a> to decrement the <i>SiloContext</i> object.


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
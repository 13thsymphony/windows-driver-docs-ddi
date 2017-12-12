---
UID: NF.ntddk.PsMakeSiloContextPermanent
title: PsMakeSiloContextPermanent function
author: windows-driver-content
description: This routine makes the slot in a silo instance read-only, allowing the object in the slot to be retrieved without affecting the reference count on that object.
old-location: kernel\psmakesilocontextpermanent.htm
old-project: kernel
ms.assetid: 74BE4FF9-0342-4942-A58F-9C6D5F76E5F0
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: PsMakeSiloContextPermanent
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
req.alt-api: PsMakeSiloContextPermanent
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

# PsMakeSiloContextPermanent function



## -description
This routine makes the slot in a silo instance read-only, allowing the object in the slot to be retrieved without affecting the reference count on that object.



## -syntax

````
NTSTATUS PsMakeSiloContextPermanent(
  _In_ PESILO Silo,
  _In_ ULONG  ContextSlot
);
````


## -parameters

### -param Silo [in]

The silo in which the slot resides. This parameter is required and it cannot be <b>NULL</b>. 


### -param ContextSlot [in]

The slot to make read-only. The slot must be previously allocated by the <a href="kernel.psallocsilocontextslot">PsAllocSiloContextSlot</a> routine.


## -returns
The following NT status codes are returned.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The slot does not contain a valid object. This is an error code.
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>The slot has not been allocated. This is an error code.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The operation completed successfully.

 


## -remarks
Before calling this routine, the slot must contain a valid object. After it completes, the <a href="kernel.psreplacesilocontext">PsReplaceSiloContext</a> and <a href="kernel.psremovesilocontext">PsRemoveSiloContext</a> routines will fail with <b>STATUS_NOT_SUPPORTED</b>. 


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
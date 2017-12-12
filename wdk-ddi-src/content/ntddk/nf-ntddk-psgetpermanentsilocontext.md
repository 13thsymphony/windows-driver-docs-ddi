---
UID: NF.ntddk.PsGetPermanentSiloContext
title: PsGetPermanentSiloContext function
author: windows-driver-content
description: This routine retrieves an object that was inserted in the Silo without incrementing the reference count.
old-location: kernel\psgetpermanentsilocontext.htm
old-project: kernel
ms.assetid: C1AEFC8F-6488-4582-9835-DAD07D4ACB17
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: PsGetPermanentSiloContext
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
req.alt-api: PsGetPermanentSiloContext
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

# PsGetPermanentSiloContext function



## -description
This routine retrieves an object that was inserted in the <i>Silo</i> without incrementing the reference count.



## -syntax

````
NTSTATUS PsGetPermanentSiloContext(
  _In_ PESILO                              Silo,
  _In_ ULONG                               ContextSlot,
       _Outptr_result_nullonfailure_ PVOID *ReturnedSiloContext
);
````


## -parameters

### -param Silo [in]

The silo in which the object was inserted. This parameter is required and it cannot be <b>NULL</b>.


### -param ContextSlot [in]

The read-only slot that was previously allocated by<a href="kernel.psallocsilocontextslot">PsAllocSiloContextSlot</a> and made read-only by <a href="kernel.psmakesilocontextpermanent">PsMakeSiloContextPermanent</a>.


### -param ReturnedSiloContext 

A pointer to a caller-allocated variable that receives the address of the existing object. This parameter is required and it cannot be <b>NULL</b>.


## -returns
The following NT status codes are returned.
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>The slot is empty. This is an error code.
<dl>
<dt><b>STATUS_NOT_SUPPORTED </b></dt>
</dl>The slot is not read-only and it cannot safely retrieve the object. This is an error code.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The operation completed successfully.

 


## -remarks
A successful call to <b>PsGetPermanentSiloContext</b> does not increment the reference count on the object that the <i>ReturnedSiloContext</i> parameter points to. The returned object pointer is valid as long as there is a valid reference on the silo object.


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
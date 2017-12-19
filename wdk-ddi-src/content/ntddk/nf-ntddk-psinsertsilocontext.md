---
UID: NF.ntddk.PsInsertSiloContext
title: PsInsertSiloContext function
author: windows-driver-content
description: This routine inserts an object in an empty slot in a Silo.
old-location: kernel\psinsertsilocontext.htm
old-project: kernel
ms.assetid: 31C7A629-3B5E-44BA-AE03-3331E3200FC6
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: PsInsertSiloContext
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
req.alt-api: PsInsertSiloContext
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

# PsInsertSiloContext function



## -description
This routine inserts an object in an empty slot in a <i>Silo</i>.



## -syntax

````
NTSTATUS PsInsertSiloContext(
  _In_ PESILO Silo,
  _In_ ULONG  ContextSlot,
  _In_ PVOID  SiloContext
);
````


## -parameters

### -param Silo [in]

A pointer to a silo.  This parameter is required and it cannot be <b>NULL</b>.


### -param ContextSlot [in]

A slot allocated by the <a href="kernel.psallocsilocontextslot">PsAllocSiloContextSlot</a> routine. 


### -param SiloContext [in]

A pointer to the object created by the <a href="kernel.pscreatesilocontext">PsCreateSiloContext</a> routine. The object must be created using the same silo pointer as the one specified in this routine. This parameter is required and it cannot be <b>NULL</b>. 


## -returns
The following NT status codes are returned.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES </b></dt>
</dl>There are no resources in the system to perform the insert. This is an error code. 
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>The slot is not empty. This is an error code. 
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
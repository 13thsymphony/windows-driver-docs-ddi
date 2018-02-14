---
UID: NF:ntddk.PsInsertPermanentSiloContext
title: PsInsertPermanentSiloContext function
author: windows-driver-content
description: This routine inserts an object in an empty slot in a Silo.
old-location: kernel\psinsertpermanentsilocontext.htm
old-project: kernel
ms.assetid: ADBAB25B-7646-4E0E-AFD8-18B87A293674
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PsInsertPermanentSiloContext, kernel.psinsertpermanentsilocontext, ntddk/PsInsertPermanentSiloContext, PsInsertPermanentSiloContext routine [Kernel-Mode Driver Architecture]
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	PsInsertPermanentSiloContext
product: Windows
targetos: Windows
req.typenames: "*PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT"
---


# PsInsertPermanentSiloContext function
This routine inserts an object in an empty slot in a <i>Silo</i>.

## Syntax

````
NTSTATUS PsInsertPermanentSiloContext(
  _In_ PESILO Silo,
  _In_ ULONG  ContextSlot,
  _In_ PVOID  SiloContext
);
````

## Parameters

`Silo`

The silo in which the object is to be inserted. This parameter is required and it cannot be <b>NULL</b>.

`ContextSlot`

The slot in which the object is to be inserted. A slot allocated by the <a href="..\ntddk\nf-ntddk-psallocsilocontextslot.md">PsAllocSiloContextSlot</a> routine.

`SiloContext`

The object to be inserted, created by the <a href="..\ntddk\nf-ntddk-pscreatesilocontext.md">PsCreateSiloContext</a> routine. The object must be created using the same silo as specified in the <i>Silo</i> parameter. This parameter is required and it cannot be <b>NULL</b>.


## Return Value

The following NT status codes are returned.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There are no resources in the system to perform the insert. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The slot is not empty. This is an error code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The operation completed successfully.

</td>
</tr>
</table>

## Remarks

A successful call to <b>PsInsertPermanentSiloContext</b> increments the reference count on <i>SiloContext</i>. If <b>PsInsertPermanentSiloContext</b> fails, the reference count remains unchanged. In either case, after the routine completes, the caller must call <a href="..\ntddk\nf-ntddk-psdereferencesilocontext.md">PsDereferenceSiloContext</a> to decrement the <i>SiloContext</i> object.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1607 Windows 10, version 1607 |
| **Target Platform** | Windows |
| **Header** | ntddk.h |
| **Library** | NtosKrnl.exe |
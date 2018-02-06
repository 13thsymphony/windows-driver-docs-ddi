---
UID: NF:ntddk.PsRemoveSiloContext
title: PsRemoveSiloContext function
author: windows-driver-content
description: This routine removes an object that was inserted in the Silo.
old-location: kernel\psremovesilocontext.htm
old-project: kernel
ms.assetid: 3323EF1B-9EB3-4D56-A9A5-0A8397F8A235
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.psremovesilocontext, PsRemoveSiloContext, PsRemoveSiloContext routine [Kernel-Mode Driver Architecture], ntddk/PsRemoveSiloContext
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
-	PsRemoveSiloContext
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# PsRemoveSiloContext function
This routine removes an object that was inserted in the <i>Silo</i>.

## Syntax

````
NTSTATUS PsRemoveSiloContext(
  _In_ PESILO                              Silo,
  _In_ ULONG                               ContextSlot,
       _Outptr_opt_result_maybenull_ PVOID *ReturnedSiloContext
);
````

## Parameters

`Silo`

The silo from which the object is to be removed. This parameter is required and it cannot be <b>NULL</b>.

`ContextSlot`

A slot allocated by the <a href="..\ntddk\nf-ntddk-psallocsilocontextslot.md">PsAllocSiloContextSlot</a> routine.

`RemovedSiloContext`

TBD


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
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The slot is empty. This is an error code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The slot is read-only and it cannot be modified. This is an error code. 

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

In a successful call to <b>PsRemoveSiloContext</b> where the <i>RemovedSiloContext</i> parameter is not <b>NULL</b> and does not point to <b>NULL</b>, the caller must decrement the object that the <i>RemovedSiloContext</i> parameter points to, by calling <a href="..\ntddk\nf-ntddk-psdereferencesilocontext.md">PsDereferenceSiloContext</a> when it is no longer needed.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1607 Windows 10, version 1607 |
| **Target Platform** | Windows |
| **Header** | ntddk.h |
| **Library** | NtosKrnl.exe |
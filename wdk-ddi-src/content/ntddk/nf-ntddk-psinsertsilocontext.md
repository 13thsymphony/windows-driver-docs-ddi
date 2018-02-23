---
UID: NF:ntddk.PsInsertSiloContext
title: PsInsertSiloContext function
author: windows-driver-content
description: This routine inserts an object in an empty slot in a Silo.
old-location: kernel\psinsertsilocontext.htm
old-project: kernel
ms.assetid: 31C7A629-3B5E-44BA-AE03-3331E3200FC6
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ntddk/PsInsertSiloContext, kernel.psinsertsilocontext, PsInsertSiloContext, PsInsertSiloContext routine [Kernel-Mode Driver Architecture]
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
-	PsInsertSiloContext
product: Windows
targetos: Windows
req.typenames: "*PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT"
---


# PsInsertSiloContext function
This routine inserts an object in an empty slot in a <i>Silo</i>.

## Syntax

````
NTSTATUS PsInsertSiloContext(
  _In_ PESILO Silo,
  _In_ ULONG  ContextSlot,
  _In_ PVOID  SiloContext
);
````

## Parameters

`Silo`

A pointer to a silo.  This parameter is required and it cannot be <b>NULL</b>.

`ContextSlot`

A slot allocated by the <a href="..\ntddk\nf-ntddk-psallocsilocontextslot.md">PsAllocSiloContextSlot</a> routine.

`SiloContext`

A pointer to the object created by the <a href="..\ntddk\nf-ntddk-pscreatesilocontext.md">PsCreateSiloContext</a> routine. The object must be created using the same silo pointer as the one specified in this routine. This parameter is required and it cannot be <b>NULL</b>.


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
<dt><b>STATUS_INSUFFICIENT_RESOURCES </b></dt>
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


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1607 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | ntddk.h |
| **Library** | NtosKrnl.exe |
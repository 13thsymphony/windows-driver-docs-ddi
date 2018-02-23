---
UID: NF:dbgeng.IDebugSymbols.ReadTypedDataVirtual
title: IDebugSymbols::ReadTypedDataVirtual method
author: windows-driver-content
description: The ReadTypedDataVirtual method reads the value of a variable in the target's virtual memory.
old-location: debugger\readtypeddatavirtual.htm
old-project: Debugger
ms.assetid: 526bebd8-95af-4f6f-a381-eb60273d1af5
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: ReadTypedDataVirtual method [Windows Debugging], IDebugSymbols interface, dbgeng/IDebugSymbols3::ReadTypedDataVirtual, ReadTypedDataVirtual method [Windows Debugging], IDebugSymbols3 interface, dbgeng/IDebugSymbols2::ReadTypedDataVirtual, ReadTypedDataVirtual method [Windows Debugging], IDebugSymbols interface [Windows Debugging], ReadTypedDataVirtual method, debugger.readtypeddatavirtual, IDebugSymbols, IDebugSymbols2 interface [Windows Debugging], ReadTypedDataVirtual method, IDebugSymbols3::ReadTypedDataVirtual, IDebugSymbols_c7a6fee6-d6bc-4dd6-923a-7e789801091f.xml, ReadTypedDataVirtual method [Windows Debugging], IDebugSymbols2 interface, IDebugSymbols2::ReadTypedDataVirtual, IDebugSymbols::ReadTypedDataVirtual, ReadTypedDataVirtual, IDebugSymbols3 interface [Windows Debugging], ReadTypedDataVirtual method, dbgeng/IDebugSymbols::ReadTypedDataVirtual
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugSymbols.ReadTypedDataVirtual
-	IDebugSymbols2.ReadTypedDataVirtual
-	IDebugSymbols3.ReadTypedDataVirtual
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# ReadTypedDataVirtual method
The <b>ReadTypedDataVirtual</b> method reads the value of a variable in the target's virtual memory.

## Syntax

````
HRESULT ReadTypedDataVirtual(
  [in]            ULONG64 Offset,
  [in]            ULONG64 Module,
  [in]            ULONG   TypeId,
  [out]           PVOID   Buffer,
  [in]            ULONG   BufferSize,
  [out, optional] PULONG  BytesRead
);
````

## Parameters

`Offset`

Specifies the location in the target's virtual address space of the variable to read.

`Module`

Specifies the base address of the module containing the type of the variable.

`TypeId`

Specifies the type ID of the type.

`Buffer`

Receives the data that is read.

`BufferSize`

Specifies the size in bytes of the buffer <i>Buffer</i>.  This is the maximum number of bytes to be read.

`BytesRead`

Receives the number of bytes that were read.  If <i>BytesRead</i> is <b>NULL</b>, this information is not returned.


## Return Value

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.  However, the buffer <i>Buffer</i> was not large enough to hold all the data and it was truncated.

</td>
</tr>
</table>
 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

## Remarks

The number of bytes this method attempts to read is the smaller of the size of the buffer and the size of the variable.

This is a convenience method.  The same result can be obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549457">GetTypeSize</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff554359">ReadVirtual</a>.

For more information about types, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558931">Types</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |
---
UID: NF:dbgeng.IDebugSymbols.WriteTypedDataPhysical
title: IDebugSymbols::WriteTypedDataPhysical method
author: windows-driver-content
description: The WriteTypedDataPhysical method writes the value of a variable in the target computer's physical memory.
old-location: debugger\writetypeddataphysical.htm
old-project: Debugger
ms.assetid: 5f29249f-bb62-45d1-aa0e-108db1d7f906
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: WriteTypedDataPhysical method [Windows Debugging], IDebugSymbols interface [Windows Debugging], WriteTypedDataPhysical method, WriteTypedDataPhysical, IDebugSymbols2 interface [Windows Debugging], WriteTypedDataPhysical method, dbgeng/IDebugSymbols3::WriteTypedDataPhysical, WriteTypedDataPhysical method [Windows Debugging], IDebugSymbols2 interface, debugger.writetypeddataphysical, IDebugSymbols2::WriteTypedDataPhysical, dbgeng/IDebugSymbols2::WriteTypedDataPhysical, IDebugSymbols_b5205296-88eb-4af8-8448-b2a79f08e7b0.xml, IDebugSymbols::WriteTypedDataPhysical, WriteTypedDataPhysical method [Windows Debugging], IDebugSymbols interface, IDebugSymbols3::WriteTypedDataPhysical, WriteTypedDataPhysical method [Windows Debugging], IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging], WriteTypedDataPhysical method, IDebugSymbols, dbgeng/IDebugSymbols::WriteTypedDataPhysical
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
-	IDebugSymbols.WriteTypedDataPhysical
-	IDebugSymbols2.WriteTypedDataPhysical
-	IDebugSymbols3.WriteTypedDataPhysical
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# WriteTypedDataPhysical method
The <b>WriteTypedDataPhysical</b> method writes the value of a variable in the target computer's physical memory.

## Syntax

````
HRESULT WriteTypedDataPhysical(
  [in]            ULONG64 Offset,
  [in]            ULONG64 Module,
  [in]            ULONG   TypeId,
  [in]            PVOID   Buffer,
  [in]            ULONG   BufferSize,
  [out, optional] PULONG  BytesWritten
);
````

## Parameters

`Offset`

Specifies the physical address in the target computer's memory of the variable.

`Module`

Specifies the base address of the module containing the type of the variable.

`TypeId`

Specifies the type ID of the type of the variable.

`Buffer`

Specifies the buffer containing the data to be written.

`BufferSize`

Specifies the size in bytes of the buffer <i>Buffer</i>.  This is the maximum number of bytes to be written.

`BytesWritten`

Receives the number of bytes that were written.  If <i>BytesWritten</i> is <b>NULL</b>, this information is not returned.


## Return Value

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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
The method was successful.  All the bytes in the buffer <i>Buffer</i> were written.  However, the buffer was smaller than the size of the specified type.

</td>
</tr>
</table>

## Remarks

This method is only available in kernel mode debugging.

The number of bytes this method attempts to write is the smaller of the size of the buffer and the size of the variable.

This is a convenience method.  The same result can be obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549457">GetTypeSize</a> and <a href="..\wdbgexts\nf-wdbgexts-writephysical.md">WritePhysical</a>.

For more information about types, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558931">Types</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |
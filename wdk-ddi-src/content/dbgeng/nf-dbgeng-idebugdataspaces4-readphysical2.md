---
UID: NF:dbgeng.IDebugDataSpaces4.ReadPhysical2
title: IDebugDataSpaces4::ReadPhysical2 method
author: windows-driver-content
description: The ReadPhysical2 method reads the target's memory from the specified physical address.
old-location: debugger\readphysical2.htm
old-project: debugger
ms.assetid: ad376a6f-b8e3-40ba-9b00-df1410c1293c
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: IDebugDataSpaces4, IDebugDataSpaces4 interface [Windows Debugging], ReadPhysical2 method, IDebugDataSpaces4::ReadPhysical2, IDebugDataSpaces_b7eb9d7f-98a3-4be4-a264-68d9ac1eaea7.xml, ReadPhysical2 method [Windows Debugging], ReadPhysical2 method [Windows Debugging], IDebugDataSpaces4 interface, ReadPhysical2,IDebugDataSpaces4.ReadPhysical2, dbgeng/IDebugDataSpaces4::ReadPhysical2, debugger.readphysical2
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugDataSpaces4.ReadPhysical2
product:
- Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# IDebugDataSpaces4::ReadPhysical2 method
The <b>ReadPhysical2</b> method reads the target's memory from the specified physical address.

## Syntax

```
HRESULT ReadPhysical2(
  ULONG64 Offset,
  ULONG   Flags,
  PVOID   Buffer,
  ULONG   BufferSize,
  PULONG  BytesRead
);
```

## Parameters

`Offset`

Specifies the physical address of the memory to read.

`Flags`

Specifies the properties of the physical memory to be read.  This must match the way the physical memory was advertised to the operating system on the target.  Possible values are listed in the following table.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_PHYSICAL_DEFAULT

</td>
<td>
Use the default memory caching.

</td>
</tr>
<tr>
<td>
DEBUG_PHYSICAL_CACHED

</td>
<td>
The physical memory is cached.

</td>
</tr>
<tr>
<td>
DEBUG_PHYSICAL_UNCACHED

</td>
<td>
The physical memory is uncached.

</td>
</tr>
<tr>
<td>
DEBUG_PHYSICAL_WRITE_COMBINED

</td>
<td>
The physical memory is write-combined.

</td>
</tr>
</table>

`Buffer`

Receives the memory that is read.

`BufferSize`

Specifies the size, in bytes, of the <i>Buffer</i> buffer.  This is the maximum number of bytes that will be read.

`BytesRead`

Receives the number of bytes read from the target's memory.  If <i>BytesRead</i> is <b>NULL</b>, this information is not returned.


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
</table>
 

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

## Remarks

This method is only available in kernel-mode debugging.

The flags DEBUG_PHYSICAL_CACHED, DEBUG_PHYSICAL_UNCACHED, and DEBUG_PHYSICAL_WRITE_COMBINED can only be used when the target is a live kernel target that is being debugged in the standard way (using a COM port, 1394 bus, or named pipe).

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550546">IDebugDataSpaces4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554313">ReadPhysical</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561441">WritePhysical2</a>
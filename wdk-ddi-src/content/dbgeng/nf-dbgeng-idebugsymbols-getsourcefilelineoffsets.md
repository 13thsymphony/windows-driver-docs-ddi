---
UID: NF:dbgeng.IDebugSymbols.GetSourceFileLineOffsets
title: IDebugSymbols::GetSourceFileLineOffsets method
author: windows-driver-content
description: The GetSourceFileLineOffsets method maps each line in a source file to a location in the target's memory.
old-location: debugger\getsourcefilelineoffsets.htm
old-project: debugger
ms.assetid: ace9e23a-d7ea-480a-8001-f25310adee22
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetSourceFileLineOffsets method [Windows Debugging], GetSourceFileLineOffsets method [Windows Debugging], IDebugSymbols interface, GetSourceFileLineOffsets method [Windows Debugging], IDebugSymbols2 interface, GetSourceFileLineOffsets method [Windows Debugging], IDebugSymbols3 interface, GetSourceFileLineOffsets,IDebugSymbols.GetSourceFileLineOffsets, IDebugSymbols, IDebugSymbols interface [Windows Debugging], GetSourceFileLineOffsets method, IDebugSymbols2 interface [Windows Debugging], GetSourceFileLineOffsets method, IDebugSymbols2::GetSourceFileLineOffsets, IDebugSymbols3 interface [Windows Debugging], GetSourceFileLineOffsets method, IDebugSymbols3::GetSourceFileLineOffsets, IDebugSymbols::GetSourceFileLineOffsets, IDebugSymbols_18a64f21-a082-4953-8d69-2b3f7d805c60.xml, dbgeng/IDebugSymbols2::GetSourceFileLineOffsets, dbgeng/IDebugSymbols3::GetSourceFileLineOffsets, dbgeng/IDebugSymbols::GetSourceFileLineOffsets, debugger.getsourcefilelineoffsets
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
-	IDebugSymbols.GetSourceFileLineOffsets
-	IDebugSymbols2.GetSourceFileLineOffsets
-	IDebugSymbols3.GetSourceFileLineOffsets
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# IDebugSymbols::GetSourceFileLineOffsets method
The <b>GetSourceFileLineOffsets</b>  method maps each line in a source file to a location in the target's memory.

## Syntax

```
HRESULT GetSourceFileLineOffsets(
  PCSTR    File,
  PULONG64 Buffer,
  ULONG    BufferLines,
  PULONG   FileLines
);
```

## Parameters

`File`

Specifies the name of the file whose lines will be turned into locations in the target's memory.  The symbols for each module in the target are queried for this file.  If the file is not located, the path is dropped and the symbols are queried again.

`Buffer`

Receives the locations in the target's memory that correspond to the lines of the source code.  The first entry returned to this array corresponds to the first line of the file, so that <code>Buffer[i]</code> contains the location for line <code>i+1</code>.  If no symbol information is available for a line, the corresponding entry in <i>Buffer</i> is set to DEBUG_INVALID_OFFSET.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.

`BufferLines`

Specifies the number of PULONG64 objects that the <i>Buffer</i> array can hold.

`FileLines`

Receives the number of lines in the source file specified by <i>File</i>.


## Return Value

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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
The method was successful.  However, the number of lines in the source file exceeded the number of entries in the <i>Buffer</i> array and some of the results were discarded.

</td>
</tr>
</table>

## Remarks

For more information about using the source path, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560141">Using Source Files</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545423">FindSourceFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548305">GetSourceEntriesByLine</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550856">IDebugSymbols</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550864">IDebugSymbols2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>
---
UID: NF:dbgeng.IDebugDataSpaces.SearchVirtual
title: IDebugDataSpaces::SearchVirtual method
author: windows-driver-content
description: The SearchVirtual method searches the target's virtual memory for a specified pattern of bytes.
old-location: debugger\searchvirtual.htm
old-project: debugger
ms.assetid: 1cb779de-fcbb-450d-9932-0cdaa9fbb1e9
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: IDebugDataSpaces, IDebugDataSpaces interface [Windows Debugging], SearchVirtual method, IDebugDataSpaces2 interface [Windows Debugging], SearchVirtual method, IDebugDataSpaces2::SearchVirtual, IDebugDataSpaces3 interface [Windows Debugging], SearchVirtual method, IDebugDataSpaces3::SearchVirtual, IDebugDataSpaces4 interface [Windows Debugging], SearchVirtual method, IDebugDataSpaces4::SearchVirtual, IDebugDataSpaces::SearchVirtual, IDebugDataSpaces_9af5d620-f8df-430c-88ab-0d4f96844499.xml, SearchVirtual method [Windows Debugging], SearchVirtual method [Windows Debugging], IDebugDataSpaces interface, SearchVirtual method [Windows Debugging], IDebugDataSpaces2 interface, SearchVirtual method [Windows Debugging], IDebugDataSpaces3 interface, SearchVirtual method [Windows Debugging], IDebugDataSpaces4 interface, SearchVirtual,IDebugDataSpaces.SearchVirtual, dbgeng/IDebugDataSpaces2::SearchVirtual, dbgeng/IDebugDataSpaces3::SearchVirtual, dbgeng/IDebugDataSpaces4::SearchVirtual, dbgeng/IDebugDataSpaces::SearchVirtual, debugger.searchvirtual
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
-	IDebugDataSpaces.SearchVirtual
-	IDebugDataSpaces2.SearchVirtual
-	IDebugDataSpaces3.SearchVirtual
-	IDebugDataSpaces4.SearchVirtual
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# IDebugDataSpaces::SearchVirtual method
The <b>SearchVirtual</b> method searches the target's virtual memory for a specified pattern of bytes.

## Syntax

```
HRESULT SearchVirtual(
  ULONG64  Offset,
  ULONG64  Length,
  PVOID    Pattern,
  ULONG    PatternSize,
  ULONG    PatternGranularity,
  PULONG64 MatchOffset
);
```

## Parameters

`Offset`

Specifies the location in the target's virtual address space to start searching for the pattern.

`Length`

Specifies how far to search for the pattern.  A successful match requires the entire pattern to be found before <i>Length</i> bytes have been examined.

`Pattern`

Specifies the pattern to search for.

`PatternSize`

Specifies the size in bytes of the pattern.  This must be a multiple of the granularity of the pattern.

`PatternGranularity`

Specifies the granularity of the pattern.  For a successful match the pattern must occur a multiple of this value after the start location.

`MatchOffset`

Receives the location in the target's virtual address space of the pattern, if it was found.


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
<dt><b>HRESULT_FROM_NT(STATUS_NO_MORE_ENTRIES)</b></dt>
</dl>
</td>
<td width="60%">
After examining <i>Length</i> bytes the pattern was not found.

</td>
</tr>
</table>

## Remarks

This method searches the target's virtual memory for the first occurrence, subject to granularity, of the pattern entirely contained in the <i>Length</i> bytes of the target's memory starting at the location <i>Offset</i>.

<i>PatternGranularity</i> can be used to ensure the alignment of the match relative to <i>Offset</i>.  For example, a value of 0x4 can be used to require alignment to a DWORD.  A value of 0x1 can be used to allow the pattern to start anywhere.

For additional options, including the ability to restrict the search to writable memory, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554755">SearchVirtual2</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550528">IDebugDataSpaces</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550531">IDebugDataSpaces2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550537">IDebugDataSpaces3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550546">IDebugDataSpaces4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554359">ReadVirtual</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554755">SearchVirtual2</a>
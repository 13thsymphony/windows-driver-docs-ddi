---
UID: NF:fltkernel.FltClose
title: FltClose function
author: windows-driver-content
description: FltClose closes a file handle that was opened by FltCreateFile or FltCreateFileEx.
old-location: ifsk\fltclose.htm
old-project: ifsk
ms.assetid: fd5967cc-fb30-4882-9567-4617b9f9e723
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FltApiRef_a_to_d_f50e2397-1161-4e6e-9688-2baa417f6845.xml, FltClose, FltClose function [Installable File System Drivers], fltkernel/FltClose, ifsk.fltclose
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltClose
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# FltClose function
<b>FltClose</b> closes a file handle that was opened by <a href="https://msdn.microsoft.com/library/windows/hardware/ff541935">FltCreateFile</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff541937">FltCreateFileEx</a>.

## Syntax

```
NTSTATUS FLTAPI FltClose(
  HANDLE FileHandle
);
```

## Parameters

`FileHandle`

Handle created by a successful call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff541935">FltCreateFile</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff541937">FltCreateFileEx</a>.


## Return Value

<b>FltClose</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
<i>FileHandle</i> was not a valid file handle. This is an error code. 

</td>
</tr>
</table>

## Remarks

<b>FltClose</b> is only for closing file handles opened by <a href="https://msdn.microsoft.com/library/windows/hardware/ff541935">FltCreateFile</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff541937">FltCreateFileEx</a>. It should not be used to close arbitrary handles.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** | FltMgr.lib |
| **DLL** | Fltmgr.sys |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541935">FltCreateFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541937">FltCreateFileEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566417">ZwClose</a>
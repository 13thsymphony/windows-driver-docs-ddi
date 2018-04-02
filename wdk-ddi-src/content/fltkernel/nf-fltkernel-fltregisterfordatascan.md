---
UID: NF:fltkernel.FltRegisterForDataScan
title: FltRegisterForDataScan function
author: windows-driver-content
description: The FltRegisterForDataScan routine enables data scanning for the volume attached to the minifilter instance.
old-location: ifsk\fltregisterfordatascan.htm
old-project: ifsk
ms.assetid: E603975A-B927-475A-9DEA-2D01C1249819
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FltRegisterForDataScan, FltRegisterForDataScan routine [Installable File System Drivers], fltkernel/FltRegisterForDataScan, ifsk.fltregisterfordatascan
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: The FltRegisterForDataScan routine is available starting with   Windows 8.
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltRegisterForDataScan
product:
- Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# FltRegisterForDataScan function
The <b>FltRegisterForDataScan</b> routine enables data scanning for the volume attached to the minifilter instance.

## Syntax

```
NTSTATUS FLTAPI FltRegisterForDataScan(
  PFLT_INSTANCE Instance
);
```

## Parameters

`Instance`

An opaque instance pointer for the minifilter driver instance to register for data scanning.


## Return Value

<b>FltRegisterForDataScan</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as one of the following. 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The filter manager does not support data scans for the volume attached to this instance.

</td>
</tr>
</table>

## Remarks

If <b>STATUS_NOT_SUPPORTED</b> is returned by <b>FltRegisterForDataScan</b>, a minifilter can still create sections for data scanning using <a href="https://msdn.microsoft.com/library/windows/hardware/ff545812">FsRtlCreateSectionForDataScan</a>. However, section access is not synchronized and conflict resolution is left to the minifilter driver.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | The FltRegisterForDataScan routine is available starting with   Windows 8.  |
| **Target Platform** | Universal |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** | FltMgr.lib |
| **DLL** | Fltmgr.sys |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406456">FltCloseSectionForDataScan</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450937">FltCreateSectionForDataScan</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545812">FsRtlCreateSectionForDataScan</a>
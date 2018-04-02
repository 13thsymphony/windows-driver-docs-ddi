---
UID: NF:fltkernel.FltSetIoPriorityHintIntoThread
title: FltSetIoPriorityHintIntoThread function
author: windows-driver-content
description: The FltSetIoPriorityHintIntoThread routine is used by a minifilter driver to set the IO priority information in a thread.
old-location: ifsk\fltsetiopriorityhintintothread.htm
old-project: ifsk
ms.assetid: 924fadbe-2703-43f8-985c-db5a7bb960a6
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FltApiRef_p_to_z_acdf2d2e-c98e-4e7d-8074-fb2b89594771.xml, FltSetIoPriorityHintIntoThread, FltSetIoPriorityHintIntoThread routine [Installable File System Drivers], fltkernel/FltSetIoPriorityHintIntoThread, ifsk.fltsetiopriorityhintintothread
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in starting with Windows Vista.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltSetIoPriorityHintIntoThread
product:
- Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# FltSetIoPriorityHintIntoThread function
The <b>FltSetIoPriorityHintIntoThread</b> routine is used by a minifilter driver to set the IO priority information in a thread.

## Syntax

```
NTSTATUS FLTAPI FltSetIoPriorityHintIntoThread(
  PETHREAD         Thread,
  IO_PRIORITY_HINT PriorityHint
);
```

## Parameters

`Thread`

A pointer to the thread to modify. This parameter is required and cannot be <b>NULL</b>.

`PriorityHint`

The  <a href="https://msdn.microsoft.com/library/windows/hardware/ff550594">IO_PRIORITY_HINT</a> enumeration value to set for the thread information pointed to by <i>Thread</i>.


## Return Value

If the IO Priority value passed to the <i>PriorityHint</i> parameter is successfully applied to the <i>Thread</i>, <b>FltSetIoPriorityHintIntoThread</b> returns STATUS_SUCCESS. Otherwise, it returns an appropriate NTSTATUS value, such as one of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER </b></dt>
</dl>
</td>
<td width="60%">
The value of the <i>PriorityHint</i> parameter is invalid. This is an error code. 

</td>
</tr>
</table>

## Remarks

This routine is NONPAGED and can be called from paging IO paths.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in starting with Windows Vista.  |
| **Target Platform** | Universal |
| **Header** | fltkernel.h (include FltKernel.h) |
| **Library** | FltMgr.lib |
| **DLL** | Fltmgr.sys |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541766">FltApplyPriorityInfoThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543065">FltGetIoPriorityHint</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543068">FltGetIoPriorityHintFromCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543074">FltGetIoPriorityHintFromFileObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543080">FltGetIoPriorityHintFromThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544354">FltRetrieveIoPriorityInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544526">FltSetIoPriorityHintIntoCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544530">FltSetIoPriorityHintIntoFileObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550594">IO_PRIORITY_HINT</a>
---
UID: NF:ntifs.CcScheduleReadAhead
title: CcScheduleReadAhead function
author: windows-driver-content
description: The CcScheduleReadAhead routine performs read-ahead (also called &#0034;lazy read&#0034;) on a cached file. CcScheduleReadAhead should never be called directly. The CcReadAhead macro should be called instead.
old-location: ifsk\ccschedulereadahead.htm
old-project: ifsk
ms.assetid: 57fbe32d-ffc8-449e-be7f-2d2a8f2a7a66
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: CcScheduleReadAhead, CcScheduleReadAhead routine [Installable File System Drivers], ccref_ae4b3e52-9f23-499f-86f1-81e813484007.xml, ifsk.ccschedulereadahead, ntifs/CcScheduleReadAhead
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	CcScheduleReadAhead
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# CcScheduleReadAhead function
The <b>CcScheduleReadAhead</b> routine performs read-ahead (also called "lazy read") on a cached file. <b>CcScheduleReadAhead</b> should never be called directly. The <b>CcReadAhead</b> macro should be called instead.

## Syntax

```
NTKERNELAPI VOID CcScheduleReadAhead(
  PFILE_OBJECT   FileObject,
  PLARGE_INTEGER FileOffset,
  ULONG          Length
);
```

## Parameters

`FileObject`

Pointer to a file object for the file on which read-ahead is to be performed.

`FileOffset`

Pointer to a variable that specifies the starting byte offset within the cached file where the last read occurred.

`Length`

Length in bytes of the range that was last read.


## Return Value

None

## Remarks

The <b>CcReadAhead</b> macro is a wrapper for <b>CcScheduleReadAhead</b>. It calls <b>CcScheduleReadAhead</b> only if <i>Length</i> &gt;= 256. Measurements have shown that calling <b>CcScheduleReadAhead</b> for smaller reads actually decreases performance.

<b>CcReadAhead</b> and <b>CcScheduleReadAhead</b> can only be called after a successful call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff539038">CcCopyRead</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff539067">CcFastCopyRead</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff539159">CcMdlRead</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539038">CcCopyRead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539067">CcFastCopyRead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539159">CcMdlRead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539200">CcScheduleReadAhead</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539203">CcSetAdditionalCacheAttributes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539224">CcSetReadAheadGranularity</a>
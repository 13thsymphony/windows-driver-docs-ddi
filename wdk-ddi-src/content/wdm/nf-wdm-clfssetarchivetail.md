---
UID: NF:wdm.ClfsSetArchiveTail
title: ClfsSetArchiveTail function
author: windows-driver-content
description: The ClfsSetArchiveTail routine sets the archive tail of a CLFS log to a specified LSN.
old-location: kernel\clfssetarchivetail.htm
old-project: kernel
ms.assetid: 58c1d222-72c5-4b40-9ae5-f633bac599f0
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: ClfsSetArchiveTail, ClfsSetArchiveTail routine [Kernel-Mode Driver Architecture], Clfs_f5685e7e-3098-461d-aff1-807011c36526.xml, kernel.clfssetarchivetail, wdm/ClfsSetArchiveTail
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.
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
req.lib: Clfs.lib
req.dll: Clfs.sys
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Clfs.sys
-	Ext-MS-Win-fs-clfs-l1-1-0.dll
api_name:
-	ClfsSetArchiveTail
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# ClfsSetArchiveTail function
The <b>ClfsSetArchiveTail</b> routine sets the archive tail of a CLFS log to a specified LSN.

## Syntax

```
CLFSUSER_API NTSTATUS ClfsSetArchiveTail(
  PLOG_FILE_OBJECT plfoLog,
  PCLFS_LSN        plsnArchiveTail
);
```

## Parameters

`plfoLog`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554316">LOG_FILE_OBJECT</a> structure that represents a CLFS log. The caller previously obtained this pointer by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff540792">ClfsCreateLogFile</a>.

`plsnArchiveTail`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541824">CLFS_LSN</a> structure that specifies the LSN that is to become the new archive tail. This must be the exact LSN of a record in the log.


## Return Value

<b>ClfsSetArchiveTail</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.

## Remarks

The <i>plsnArchiveTail</i> value specifies where archiving starts in the log. The next archiving will start at <u>or before</u> this LSN.

For an explanation of CLFS concepts and terminology, see <a href="https://msdn.microsoft.com/a9685648-b08c-48ca-b020-e683068f2ea2">Common Log File System</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Server 2003 R2, Windows Vista, and later versions of Windows.  |
| **Target Platform** | Desktop |
| **Header** | wdm.h (include Wdm.h) |
| **Library** | Clfs.lib |
| **DLL** | Clfs.sys |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540773">ClfsAdvanceLogBase</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540792">ClfsCreateLogFile</a>



<a href="https://msdn.microsoft.com/7e3b2eed-2de6-4459-a125-a27d9db69c93">ClfsSetEndOfLog </a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554316">LOG_FILE_OBJECT</a>
---
UID: NF:wdm.ClfsDeleteLogByPointer
title: ClfsDeleteLogByPointer function
author: windows-driver-content
description: The ClfsDeleteLogByPointer routine marks a CLFS stream for deletion.
old-location: kernel\clfsdeletelogbypointer.htm
old-project: kernel
ms.assetid: da6e4133-a2ba-4f8c-9490-e1f9b453b6e2
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: ClfsDeleteLogByPointer, ClfsDeleteLogByPointer routine [Kernel-Mode Driver Architecture], Clfs_d5571c5c-19a0-4113-8401-910721d76191.xml, kernel.clfsdeletelogbypointer, wdm/ClfsDeleteLogByPointer
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
-	ClfsDeleteLogByPointer
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# ClfsDeleteLogByPointer function
The <b>ClfsDeleteLogByPointer</b> routine marks a CLFS stream for deletion.

## Syntax

```
CLFSUSER_API NTSTATUS ClfsDeleteLogByPointer(
  PLOG_FILE_OBJECT plfoLog
);
```

## Parameters

`plfoLog`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554316">LOG_FILE_OBJECT</a> structure that represents an open instance of the stream to be deleted. The caller previously obtained this pointer by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff540792">ClfsCreateLogFile</a>.


## Return Value

<b>ClfsDeleteLogByPointer</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.

## Remarks

<b>ClfsDeleteLogByPointer</b> marks a stream for deletion but does not close the log file object pointed to by <i>plfoLog</i>. To close a log file object, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff540789">ClfsCloseLogFileObject</a>. A stream marked for deletion is deleted after all log file objects associated with the stream are closed.

A CLFS stream marked for deletion will refuse subsequent requests to open the stream.

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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540792">ClfsCreateLogFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541539">ClfsDeleteLogFile</a>
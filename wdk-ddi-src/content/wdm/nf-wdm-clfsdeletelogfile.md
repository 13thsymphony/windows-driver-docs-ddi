---
UID: NF:wdm.ClfsDeleteLogFile
title: ClfsDeleteLogFile function
author: windows-driver-content
description: The ClfsDeleteLogFile routine marks a CLFS stream for deletion.
old-location: kernel\clfsdeletelogfile.htm
old-project: kernel
ms.assetid: a8c90199-e938-45bb-9356-48591e127eed
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: ClfsDeleteLogFile, ClfsDeleteLogFile routine [Kernel-Mode Driver Architecture], Clfs_0b23f7ac-c175-4eaf-b6c9-9b23b6ebe7e3.xml, kernel.clfsdeletelogfile, wdm/ClfsDeleteLogFile
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
-	ClfsDeleteLogFile
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# ClfsDeleteLogFile function
The <b>ClfsDeleteLogFile</b> routine marks a CLFS stream for deletion.

## Syntax

```
CLFSUSER_API NTSTATUS ClfsDeleteLogFile(
  PUNICODE_STRING puszLogFileName,
  PVOID           pvReserved,
  ULONG           fLogOptionFlag,
  PVOID           pvContext,
  ULONG           cbContext
);
```

## Parameters

`puszLogFileName`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure that supplies the name of the CLFS stream to be deleted. 

If the stream to be deleted is the only stream of a dedicated log, the name has the form log:<i>physical log name</i>, where <i>physical log name</i> is the path name of the physical log on the underlying file system.

If the stream to be deleted is one of the streams of a multiplexed log, the name has the form log:<i>physical log name</i>::<i>stream name</i>, where <i>physical log name</i> is the path name of  the physical log on the underlying file system and <i>stream name</i> is the unique name of the stream to be deleted.

`pvReserved`

TBD

`fLogOptionFlag`

A value that indicates the relationship between CLFS and the component that is deleting the log. For a list of possible values, see the description of the <i>fLogOptionFlag</i> parameter of the <b>ClfsCreateLogFile</b> routine.

`pvContext`

A pointer to a context. The way the context is interpreted depends on the value passed in <i>fLogOptionFlag</i>.

`cbContext`

The size, in bytes, of the context pointed to by <i>pvContex</i>t. If <i>pvContext</i> is not <b>NULL</b>, this parameter must be greater than zero.


## Return Value

<b>ClfsDeleteLogFile</b> returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in Ntstatus.h.

## Remarks

The Common Log File System (CLFS) uses the LOG_FILE_OBJECT structure to represent logs. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff540792">ClfsCreateLogFile</a> function returns a pointer to LOG_FILE_OBJECT, which clients then pass to other CLFS functions.

CLFS clients do not directly access the members of a LOG_FILE_OBJECT structure. For information about the members, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545834">FILE_OBJECT</a>.



<b>ClfsDeleteLogFile</b> marks a stream for deletion but does not close any log file objects that are currently open. To close a log file object, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff540789">ClfsCloseLogFileObject</a>. A stream marked for deletion is deleted after all log file objects associated with the stream are closed.

A CLFS stream marked for deletion will refuse subsequent requests to open the stream.

The name of a physical CLFS log does not include the .blf extension.

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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540787">ClfsCloseAndResetLogFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540789">ClfsCloseLogFileObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540792">ClfsCreateLogFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541529">ClfsDeleteLogByPointer</a>
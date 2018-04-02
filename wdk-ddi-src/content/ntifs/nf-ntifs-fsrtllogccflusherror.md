---
UID: NF:ntifs.FsRtlLogCcFlushError
title: FsRtlLogCcFlushError function
author: windows-driver-content
description: The FsRtlLogCcFlushError routine logs a lost delayed-write error and displays a dialog box to the user.
old-location: ifsk\fsrtllogccflusherror.htm
old-project: ifsk
ms.assetid: e516758d-d1fe-4977-93bb-f427972fdd3c
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FsRtlLogCcFlushError, FsRtlLogCcFlushError routine [Installable File System Drivers], fsrtlref_5e72d84c-d788-4b6d-b5fe-3e9b06b0e074.xml, ifsk.fsrtllogccflusherror, ntifs/FsRtlLogCcFlushError
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating system.
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	FsRtlLogCcFlushError
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# FsRtlLogCcFlushError function
The <b>FsRtlLogCcFlushError</b> routine logs a lost delayed-write error and displays a dialog box to the user.

## Syntax

```
NTKERNELAPI NTSTATUS FsRtlLogCcFlushError(
  PUNICODE_STRING          FileName,
  PDEVICE_OBJECT           DeviceObject,
  PSECTION_OBJECT_POINTERS SectionObjectPointer,
  NTSTATUS                 FlushError,
  ULONG                    Flags
);
```

## Parameters

`FileName`

The name of the file that could not be flushed.

`DeviceObject`

A pointer to the device object that this log entry should be filed against.

`SectionObjectPointer`

A pointer to the section object for the file on which the flush failed.

`FlushError`

The error returned by the call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff539082">CcFlushCache</a>.

`Flags`

A value of 0 or a bitwise combination of one or more of the following flags:

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FSRTL_CC_FLUSH_ERROR_FLAG_NO_HARD_ERROR

</td>
<td>
Suppresses presentation of an informational dialog box to the user.

</td>
</tr>
<tr>
<td>
FSRTL_CC_FLUSH_ERROR_FLAG_NO_LOG_ENTRY

</td>
<td>
Suppresses generation of a system error log entry.

</td>
</tr>
</table>


## Return Value

The <b>FsRtlLogCcFlushError</b> routine returns STATUS_SUCCESS on success or another NTSTATUS value, such as STATUS_INSUFFICIENT_RESOURCES.

## Remarks

Unless the call includes appropriate <i>Flags</i>, the <b>FsRtlLogCcFlushError</b> routine uses <a href="https://msdn.microsoft.com/library/windows/hardware/ff549488">IoRaiseInformationalHardError</a> to display a dialog box to the user, including the specific error and <i>FileName</i>, and uses <a href="https://msdn.microsoft.com/library/windows/hardware/ff550527">IoWriteErrorLogEntry</a> logs the error. 

If the entire <i>FileName</i> cannot fit within the log buffer, the routine inserts an ellipsis into the file name.

If the cache still has pages that have been modified, the error is not fatal. The routine returns to the caller without logging an error or displaying the dialog box. 

If the error is fatal, the routine increments the lost delayed write counter in the processor control block (<a href="https://msdn.microsoft.com/139a10e9-203b-499b-9291-8537eae9189c">PRCB</a>). This counter can be used in troubleshooting lost delayed write errors.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating system.  |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include FltKernel.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539082">CcFlushCache</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549488">IoRaiseInformationalHardError</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550527">IoWriteErrorLogEntry</a>
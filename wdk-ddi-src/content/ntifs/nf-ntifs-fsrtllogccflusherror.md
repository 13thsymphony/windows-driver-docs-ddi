---
UID : NF:ntifs.FsRtlLogCcFlushError
title : FsRtlLogCcFlushError function
author : windows-driver-content
description : The FsRtlLogCcFlushError routine logs a lost delayed-write error and displays a dialog box to the user.
old-location : ifsk\fsrtllogccflusherror.htm
old-project : ifsk
ms.assetid : e516758d-d1fe-4977-93bb-f427972fdd3c
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : FsRtlLogCcFlushError
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntifs.h
req.include-header : FltKernel.h, Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating system.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : FsRtlLogCcFlushError
req.alt-loc : NtosKrnl.exe
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : <= APC_LEVEL
req.typenames : TOKEN_TYPE
---


# FsRtlLogCcFlushError function
The <b>FsRtlLogCcFlushError</b> routine logs a lost delayed-write error and displays a dialog box to the user.

## Syntax

````
NTSTATUS FsRtlLogCcFlushError(
  _In_ PUNICODE_STRING          FileName,
  _In_ PDEVICE_OBJECT           DeviceObject,
  _In_ PSECTION_OBJECT_POINTERS SectionObjectPointer,
  _In_ NTSTATUS                 FlushError,
  _In_ ULONG                    Flags
);
````

## Parameters

`FileName`

The name of the file that could not be flushed.

`DeviceObject`

A pointer to the device object that this log entry should be filed against.

`SectionObjectPointer`

A pointer to the section object for the file on which the flush failed.

`FlushError`

The error returned by the call to <a href="..\ntifs\nf-ntifs-ccflushcache.md">CcFlushCache</a>.

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

Unless the call includes appropriate <i>Flags</i>, the <b>FsRtlLogCcFlushError</b> routine uses <a href="..\ntddk\nf-ntddk-ioraiseinformationalharderror.md">IoRaiseInformationalHardError</a> to display a dialog box to the user, including the specific error and <i>FileName</i>, and uses <a href="..\ntifs\nf-ntifs-iowriteerrorlogentry.md">IoWriteErrorLogEntry</a> logs the error. 

If the entire <i>FileName</i> cannot fit within the log buffer, the routine inserts an ellipsis into the file name.

If the cache still has pages that have been modified, the error is not fatal. The routine returns to the caller without logging an error or displaying the dialog box. 

If the error is fatal, the routine increments the lost delayed write counter in the processor control block (<a href="wdkgloss.p#wdkgloss.prcb#wdkgloss.prcb"><i>PRCB</i></a>). This counter can be used in troubleshooting lost delayed write errors.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntifs.h (include FltKernel.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | <= APC_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\ntifs\nf-ntifs-ccflushcache.md">CcFlushCache</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-ioraiseinformationalharderror.md">IoRaiseInformationalHardError</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-iowriteerrorlogentry.md">IoWriteErrorLogEntry</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlLogCcFlushError routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
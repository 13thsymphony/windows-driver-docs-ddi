---
UID: NF:ntddk.KeExpandKernelStackAndCallout
title: KeExpandKernelStackAndCallout function
author: windows-driver-content
description: The KeExpandKernelStackAndCallout routine calls a routine with a guaranteed amount of stack space.
old-location: kernel\keexpandkernelstackandcallout.htm
old-project: kernel
ms.assetid: afa27127-b427-4831-b5f5-3e293738c275
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: KeExpandKernelStackAndCallout, KeExpandKernelStackAndCallout routine [Kernel-Mode Driver Architecture], k105_37fc85c2-2317-41a2-9daa-766c3ccf343f.xml, kernel.keexpandkernelstackandcallout, ntddk/KeExpandKernelStackAndCallout
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Server 2003 on x64-based processors, and starting with Windows Vista on all processors.
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
-	KeExpandKernelStackAndCallout
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# KeExpandKernelStackAndCallout function
The <b>KeExpandKernelStackAndCallout</b> routine calls a routine with a guaranteed amount of stack space.

## Syntax

````
NTSTATUS KeExpandKernelStackAndCallout(
  _In_     PEXPAND_STACK_CALLOUT Callout,
  _In_opt_ PVOID                 Parameter,
  _In_     SIZE_T                Size
);
````

## Parameters

`Callout`

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff545494">ExpandedStackCall</a> routine.

`Size`

Specifies the number of bytes on the stack to provide to the <i>ExpandedStackCall</i> routine. This value must be large enough to accommodate the stack usage of the <i>ExpandedStackCall</i> routine and any call that this routine might make. This value must not exceed MAXIMUM_EXPANSION_SIZE.

`Parameter`

Specifies the parameter to pass to the <i>ExpandedStackCall</i> routine.


## Return Value

<b>KeExpandKernelStackAndCallout</b> returns STATUS_SUCCESS if the operation succeeds or an appropriate NTSTATUS value if the operation fails.

## Remarks

<b>KeExpandKernelStackAndCallout</b> expands the kernel stack by <i>Size</i> bytes for use by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545494">ExpandedStackCall</a> routine. If there is not enough space available on the stack, <b>KeExpandKernelStackAndCallout</b> allocates a new kernel stack segment. The routine then calls the <i>ExpandedStackCall</i> routine.

In Windows 7, Windows Server 2008 R2, and later versions of Windows, consider using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552036">KeExpandKernelStackAndCalloutEx</a> routine instead of <b>KeExpandKernelStackAndCallout</b>. <b>KeExpandKernelStackAndCalloutEx</b> is similar to <b>KeExpandKernelStackAndCallout</b> but has additional parameters and can be called at IRQL &lt;= DISPATCH_LEVEL.

The calling thread must not call the <a href="..\wdm\nf-wdm-psterminatesystemthread.md">PsTerminateSystemThread</a> routine until the thread's <i>ExpandedStackCall</i> routine returns. <b>PsTerminateSystemThread</b> checks to determine if the <i>ExpandedStackCall</i> routine is still active and, if it is, causes a bug check.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows Server 2003 on x64-based processors, and starting with Windows Vista on all processors.  |
| **Target Platform** | Universal |
| **Header** | ntddk.h (include Ntddk.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545494">ExpandedStackCall</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552036">KeExpandKernelStackAndCalloutEx</a>



<a href="..\wdm\nf-wdm-psterminatesystemthread.md">PsTerminateSystemThread</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeExpandKernelStackAndCallout routine%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
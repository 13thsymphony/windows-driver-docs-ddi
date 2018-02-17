---
UID: NF:wdm.DbgBreakPointWithStatus
title: DbgBreakPointWithStatus function
author: windows-driver-content
description: The DbgBreakPointWithStatus routine breaks into the kernel debugger and sends the value of Status to the debugger.
old-location: devtest\dbgbreakpointwithstatus.htm
old-project: devtest
ms.assetid: d508c9de-5fae-47c1-88fa-df9048662419
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: DbgBreakPointWithStatus
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows 2000 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DbgBreakPointWithStatus
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: DebugBreakUsage
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ntdll.lib (user mode); NtosKrnl.lib (kernel mode)
req.dll: NtosKrnl.exe
req.irql: 
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# DbgBreakPointWithStatus function
The <b>DbgBreakPointWithStatus</b> routine breaks into the kernel debugger and sends the value of <i>Status</i> to the debugger.

## Syntax

````
NTSYSAPI VOID DbgBreakPointWithStatus(
  _In_ ULONG Status
);
````

## Parameters

`Status`

Specifies a ULONG value that is sent to the debugger (for example, a status code or an address).


## Return Value

None

## Remarks

<b>DbgBreakPointWithStatus</b> is identical to <b>DbgBreakPoint</b>, except for the <i>Status</i> message.

On x86 computers, the <i>Status</i> parameter is stored in the <b>eax</b> register. On machines that have register calling conventions, <i>Status</i> is stored in the first argument register.

This routine raises an exception that is handled by the kernel debugger if one is installed; otherwise it is handled by the debug system. If a debugger is not connected to the system, the exception can be handled in the standard way.

In kernel mode, a break exception that is not handled will cause a bug check. You can, however, connect a kernel-mode debugger to a target computer that has stopped responding and has kernel debugging enabled. For more information, see <a href="https://msdn.microsoft.com/938ef180-84de-442f-9b6c-1138c2fc8d5a">Windows Debugging</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows 2000 and later.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h) |
| **Library** | Ntdll.lib (user mode); NtosKrnl.lib (kernel mode) |
| **DLL** | NtosKrnl.exe |
| **DDI compliance rules** | DebugBreakUsage |

## See Also

<dl>
<dt>
<a href="..\wdm\nf-wdm-dbgbreakpoint.md">DbgBreakPoint</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548063">KdBreakPoint</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-kdbreakpointwithstatus.md">KdBreakPointWithStatus</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [devtest\devtest]:%20DbgBreakPointWithStatus routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
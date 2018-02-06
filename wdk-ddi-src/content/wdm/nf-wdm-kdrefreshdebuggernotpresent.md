---
UID: NF:wdm.KdRefreshDebuggerNotPresent
title: KdRefreshDebuggerNotPresent function
author: windows-driver-content
description: The KdRefreshDebuggerNotPresent macro refreshes the value of the KD_DEBUGGER_NOT_PRESENT global kernel variable.
old-location: devtest\kdrefreshdebuggernotpresent.htm
old-project: devtest
ms.assetid: 3b43943d-99b7-4d60-96fe-019f4ba2b809
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: KdRefreshDebuggerNotPresent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows Server 2003 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KdRefreshDebuggerNotPresent
req.alt-loc: NtosKrnl.exe
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
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# KdRefreshDebuggerNotPresent function
The <b>KdRefreshDebuggerNotPresent</b> macro refreshes the value of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548125">KD_DEBUGGER_NOT_PRESENT</a> global kernel variable.

## Syntax

````
NTKERNELAPI BOOLEAN KdRefreshDebuggerNotPresent(void);
````

## Parameters

This function has no parameters.

## Return Value

<b>KdRefreshDebuggerNotPresent</b> returns the value of KD_DEBUGGER_NOT_PRESENT.

<b>KdRefreshDebuggerNotPresent</b> returns the value of KD_DEBUGGER_NOT_PRESENT.

<b>KdRefreshDebuggerNotPresent</b> returns the value of KD_DEBUGGER_NOT_PRESENT.

## Remarks

When <b>KdRefreshDebuggerNotPresent</b> is called, it forces the value of KD_DEBUGGER_NOT_PRESENT to be updated to reflect whether a kernel debugger is currently attached. This updated value is also used as the return value of this routine.

If a kernel debugger was recently attached or removed, the value of KD_DEBUGGER_NOT_PRESENT may not reflect the new state. If you suspect this has happened, you should call <b>KdRefreshDebuggerNotPresent</b> to refresh the value of this variable. After this call, you may use either the value of KD_DEBUGGER_NOT_PRESENT or the return value of <b>KdRefreshDebuggerNotPresent</b> to determine if the kernel debugger is present.

KD_DEBUGGER_NOT_PRESENT can be modified by Windows or any other kernel-mode binary. Therefore, it is possible that the most recent return value of <b>KdRefreshDebuggerNotPresent</b> may not match the current value of KD_DEBUGGER_NOT_PRESENT.

The following sample shows how to use <b>KdRefreshDebuggerNotPresent</b>:

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows Server 2003 and later. Available in Microsoft Windows Server 2003 and later. |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |

## See Also

<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541860">Determining if a Debugger is Attached</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548118">KD_DEBUGGER_ENABLED</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548125">KD_DEBUGGER_NOT_PRESENT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [devtest\devtest]:%20KdRefreshDebuggerNotPresent function%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
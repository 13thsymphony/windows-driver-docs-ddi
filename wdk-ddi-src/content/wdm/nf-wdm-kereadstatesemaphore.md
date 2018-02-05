---
UID : NF:wdm.KeReadStateSemaphore
title : KeReadStateSemaphore function
author : windows-driver-content
description : The KeReadStateSemaphore routine returns the current state, signaled or not-signaled, of the specified semaphore object.
old-location : kernel\kereadstatesemaphore.htm
old-project : kernel
ms.assetid : e88c89fb-c308-4c6d-a67d-c8f98d539a43
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : kernel.kereadstatesemaphore, KeReadStateSemaphore routine [Kernel-Mode Driver Architecture], wdm/KeReadStateSemaphore, KeReadStateSemaphore, k105_cc608a62-f747-4d8c-a4f8-b6df51a4d5dd.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : Available starting with Windows 2000.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : HwStorPortProhibitedDDIs
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : Any level
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# KeReadStateSemaphore function
The <b>KeReadStateSemaphore</b> routine returns the current state, signaled or not-signaled, of the specified semaphore object.

## Syntax

````
LONG KeReadStateSemaphore(
  _In_ PRKSEMAPHORE Semaphore
);
````

## Parameters

`Semaphore`

Pointer to an initialized semaphore object for which the caller provides the storage.


## Return Value

If the return value is zero, the semaphore object is set to a not-signaled state.

## Remarks

This routine provides an efficient way to poll the signal state of a semaphore. <b>KeReadStateSemaphore</b> reads the state of the semaphore without synchronizing its access to the semaphore. Do not assume that accesses of a semaphore state by <b>KeReadStateSemaphore</b> are mutually exclusive of accesses by routines, such as <a href="..\wdm\nf-wdm-kereleasesemaphore.md">KeReleaseSemaphore</a> and <a href="..\wdm\nf-wdm-kewaitforsingleobject.md">KeWaitForSingleObject</a>, that do synchronize their access to the semaphore state.

For more information about semaphore objects, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563719">Semaphore Objects</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000. Available starting with Windows 2000. |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | Any level |
| **DDI compliance rules** | HwStorPortProhibitedDDIs |

## See Also

<a href="..\wdm\nf-wdm-keinitializesemaphore.md">KeInitializeSemaphore</a>

<a href="..\wdm\nf-wdm-kewaitforsingleobject.md">KeWaitForSingleObject</a>

<a href="..\wdm\nf-wdm-kereleasesemaphore.md">KeReleaseSemaphore</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeReadStateSemaphore routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
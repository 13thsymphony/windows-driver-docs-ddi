---
UID: NF:ntifs.IoGetRequestorProcess
title: IoGetRequestorProcess function
author: windows-driver-content
description: The IoGetRequestorProcess routine returns a process pointer for the thread that originally requested a given I/O operation.
old-location: ifsk\iogetrequestorprocess.htm
old-project: ifsk
ms.assetid: 456e2354-1362-43f7-a2b0-3b3bec49b522
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IoGetRequestorProcess, IoGetRequestorProcess routine [Installable File System Drivers], ifsk.iogetrequestorprocess, ioref_5c1e0075-08db-4db9-aa0c-fa28dced1202.xml, ntifs/IoGetRequestorProcess
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoGetRequestorProcess
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# IoGetRequestorProcess function
The <b>IoGetRequestorProcess</b> routine returns a process pointer for the thread that originally requested a given I/O operation.

## Syntax

```
NTKERNELAPI PEPROCESS IoGetRequestorProcess(
  PIRP Irp
);
```

## Parameters

`Irp`

A pointer to the I/O request packet (IRP) for the I/O operation.


## Return Value

<b>IoGetRequestorProcess</b> returns a process pointer for the thread that requested the I/O operation. If the IRP is not associated with any thread, <b>IoGetRequestorProcess</b> returns <b>NULL</b>.

## Remarks

Staring with Windows Vista. <b>IoGetRequestorProcess</b> returns a pointer to the process to which the thread is currently attached. For IRPs queued for file objects, such as for completion port I/O, <b>IoGetRequestorProcess</b> returns a pointer to the issuing process. If no thread is attached,  <b>IoGetRequestorProcess</b> returns a pointer to the process that created the thread.

On  Windows XP, <b>IoGetRequestorProcess</b> returns a pointer to the process to which the thread is currently attached.<div class="alert"><b>Note</b>  On Windows XP, in cases where an IRP contains a non-NULL thread but has no thread attached, <b>IoGetRequestorProcess</b> will attempt to access  the process information for an undefined thread. This presents a possible bug check condition if <b>IoGetRequestorProcess</b> is called without exception handling or at too high of an IRQL.</div>
<div> </div>


Prior to Windows XP, <b>IoGetRequestorProcess</b> returns a pointer to the process that created the thread. 

An IRP is automatically associated with a thread if it is issued by the I/O Manager or obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff548310">IoBuildAsynchronousFsdRequest</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff548330">IoBuildSynchronousFsdRequest</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548318">IoBuildDeviceIoControlRequest</a>. 

For more information about using system threads and managing synchronization within a nonarbitrary thread context, see <a href="https://msdn.microsoft.com/fbd8aadd-5a24-48c9-9865-80cc7dc97316">Driver Threads, Dispatcher Objects, and Resources</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548310">IoBuildAsynchronousFsdRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548318">IoBuildDeviceIoControlRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548330">IoBuildSynchronousFsdRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548391">IoGetRequestorProcessId</a>
---
UID: NF:ntifs.IoGetRequestorProcessId
title: IoGetRequestorProcessId function
author: windows-driver-content
description: The IoGetRequestorProcessId routine returns the unique 32-bit process ID for the thread that originally requested a given I/O operation.
old-location: ifsk\iogetrequestorprocessid.htm
old-project: ifsk
ms.assetid: 73fe40ee-f1fe-419b-a866-6c40604f7716
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IoGetRequestorProcessId, IoGetRequestorProcessId routine [Installable File System Drivers], ifsk.iogetrequestorprocessid, ioref_a08b37d7-b999-4e40-a0aa-c62744fee6dd.xml, ntifs/IoGetRequestorProcessId
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows 2000 and later.
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
-	IoGetRequestorProcessId
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# IoGetRequestorProcessId function
The <b>IoGetRequestorProcessId</b> routine returns the unique 32-bit process ID for the thread that originally requested a given I/O operation.

## Syntax

```
NTKERNELAPI ULONG IoGetRequestorProcessId(
  PIRP Irp
);
```

## Parameters

`Irp`

A pointer to the I/O request packet (IRP) for the specified I/O operation.


## Return Value

<b>IoGetRequestorProcessId</b> returns the process ID for the thread that requested the I/O operation. If the IRP is not associated with any thread, <b>IoGetRequestorProcessId</b> returns zero.

## Remarks

On Microsoft Windows XP and later, <b>IoGetRequestorProcessId</b> returns the process ID for the process to which the thread is currently attached. 

On Microsoft Windows 2000 and earlier, <b>IoGetRequestorProcessId</b> returns the process ID for the process that created the thread. 

For more information about using system threads and managing synchronization within a nonarbitrary thread context, see <a href="https://msdn.microsoft.com/fbd8aadd-5a24-48c9-9865-80cc7dc97316">Driver Threads, Dispatcher Objects, and Resources</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | This routine is available on Microsoft Windows 2000 and later.  |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548385">IoGetRequestorProcess</a>
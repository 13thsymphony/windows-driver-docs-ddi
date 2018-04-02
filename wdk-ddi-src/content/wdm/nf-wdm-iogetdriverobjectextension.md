---
UID: NF:wdm.IoGetDriverObjectExtension
title: IoGetDriverObjectExtension function
author: windows-driver-content
description: The IoGetDriverObjectExtension routine retrieves a previously allocated per-driver context area.
old-location: kernel\iogetdriverobjectextension.htm
old-project: kernel
ms.assetid: ce983953-53fc-4a32-8072-8a9f74d11ae3
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: IoGetDriverObjectExtension, IoGetDriverObjectExtension routine [Kernel-Mode Driver Architecture], k104_37d4bd5d-6090-49b8-ab45-c898871f22e8.xml, kernel.iogetdriverobjectextension, wdm/IoGetDriverObjectExtension
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
-	IoGetDriverObjectExtension
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# IoGetDriverObjectExtension function
The <b>IoGetDriverObjectExtension</b> routine retrieves a previously allocated per-driver context area.

## Syntax

```
NTKERNELAPI PVOID IoGetDriverObjectExtension(
  PDRIVER_OBJECT DriverObject,
  PVOID          ClientIdentificationAddress
);
```

## Parameters

`DriverObject`

Specifies the driver object with which the context area is associated.

`ClientIdentificationAddress`

Specifies the unique identifier, provided when it was allocated, of the context area to be retrieved.


## Return Value

<b>IoGetDriverObjectExtension</b> returns a pointer to the context area, if any or returns <b>NULL</b>.

## Remarks

Drivers call <b>IoGetDriverObjectExtension</b> to retrieve a pointer to a previously allocated extension area.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548233">IoAllocateDriverObjectExtension</a>
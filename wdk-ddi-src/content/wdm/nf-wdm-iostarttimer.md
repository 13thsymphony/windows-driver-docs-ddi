---
UID: NF:wdm.IoStartTimer
title: IoStartTimer function
author: windows-driver-content
description: The IoStartTimer routine enables the timer associated with a given device object so the driver-supplied IoTimer routine is called once per second.
old-location: kernel\iostarttimer.htm
old-project: kernel
ms.assetid: 2e13d7da-7ef3-4c2e-b028-f7d37548c208
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: IoStartTimer, IoStartTimer routine [Kernel-Mode Driver Architecture], k104_bca7aa97-41e1-48e4-96df-52dd6109cd51.xml, kernel.iostarttimer, wdm/IoStartTimer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
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
-	IoStartTimer
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# IoStartTimer function
The <b>IoStartTimer</b> routine enables the timer associated with a given device object so the driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff550381">IoTimer</a> routine is called once per second.

## Syntax

```
NTKERNELAPI VOID IoStartTimer(
  PDEVICE_OBJECT DeviceObject
);
```

## Parameters

`DeviceObject`

Pointer to a device object whose timer routine is to be called.


## Return Value

None

## Remarks

The driver must already have set up the IoTimer routine for the <i>DeviceObject</i> by calling <b>IoInitializeTimer</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Windows |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549344">IoInitializeTimer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550377">IoStopTimer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550381">IoTimer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552130">KeInitializeDpc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552168">KeInitializeTimer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553286">KeSetTimer</a>
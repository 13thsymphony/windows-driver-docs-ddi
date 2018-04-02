---
UID: NF:wdm.KeDeregisterProcessorChangeCallback
title: KeDeregisterProcessorChangeCallback function
author: windows-driver-content
description: The KeDeregisterProcessorChangeCallback routine unregisters a callback function that was previously registered with the operating system by calling the KeRegisterProcessorChangeCallback routine.
old-location: kernel\kederegisterprocessorchangecallback.htm
old-project: kernel
ms.assetid: 69b0f360-dfe5-4e1f-bdcb-0f908ed129a7
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: KeDeregisterProcessorChangeCallback, KeDeregisterProcessorChangeCallback routine [Kernel-Mode Driver Architecture], k105_d3e135a0-4eca-4879-97cc-946ad22693db.xml, kernel.kederegisterprocessorchangecallback, wdm/KeDeregisterProcessorChangeCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Server 2008 and later versions of Windows.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeDeregisterProcessorChangeCallback
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# KeDeregisterProcessorChangeCallback function
The <b>KeDeregisterProcessorChangeCallback</b> routine unregisters a callback function that was previously registered with the operating system by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553120">KeRegisterProcessorChangeCallback</a> routine.

## Syntax

```
void KeDeregisterProcessorChangeCallback(
  PVOID CallbackHandle
);
```

## Parameters

`CallbackHandle`

The callback registration handle that was returned by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553120">KeRegisterProcessorChangeCallback</a> routine when the callback function was registered with the operating system.


## Return Value

None

## Remarks

A device driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553120">KeRegisterProcessorChangeCallback</a> routine to register a callback function with the operating system so that the operating system will notify the driver when a new processor is added to the hardware partition. When the device driver no longer needs to receive notification when new processors are added to the hardware paritition, it calls the <b>KeDeregisterProcessorChangeCallback</b> routine to unregister the callback function. A callback function that has been registered for notification of processor changes must be unregistered before the device driver is unloaded from the operating system.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Server 2008 and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553120">KeRegisterProcessorChangeCallback</a>
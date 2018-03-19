---
UID: NF:wdm.PoQueryWatchdogTime
title: PoQueryWatchdogTime function
author: windows-driver-content
description: The PoQueryWatchdogTime routine indicates whether the power manager has enabled a watchdog time-out counter for any power IRP that is currently assigned to the device stack.
old-location: kernel\poquerywatchdogtime.htm
old-project: kernel
ms.assetid: 4833d4e2-295a-4d38-9ebf-8af68eeff948
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: PoQueryWatchdogTime, PoQueryWatchdogTime routine [Kernel-Mode Driver Architecture], kernel.poquerywatchdogtime, portn_1fe369ed-f8f0-4459-943f-a624764c279b.xml, wdm/PoQueryWatchdogTime
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 7.
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
-	PoQueryWatchdogTime
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# PoQueryWatchdogTime function
The <b>PoQueryWatchdogTime</b> routine indicates whether the power manager has enabled a watchdog time-out counter for any power IRP that is currently assigned to the device stack.

## Syntax

````
BOOLEAN PoQueryWatchdogTime(
  _In_  PDEVICE_OBJECT Pdo,
  _Out_ PULONG         SecondsRemaining
);
````

## Parameters

`Pdo`

A pointer to a physical device object (PDO). This parameter points to a <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure that represents a physical device.

`SecondsRemaining`

A pointer to a location into which the routine writes the time, in seconds, that remains before the next power watchdog time-out is set to occur.


## Return Value

<b>PoQueryWatchdogTime</b> returns <b>TRUE</b> if a watchdog-enabled power IRP is currently assigned to the device stack. Otherwise, it returns <b>FALSE</b>.

## Remarks

This routine enables kernel-mode drivers to monitor watchdog time-out counters that the power manager has enabled to keep track of power IRPs that it has issued. If one or more watchdog time-out counters are currently enabled, the routine returns <b>TRUE</b> and provides the amount of time that remains before the next time-out.

For example, a driver that experiences delays when shutting down a device can call this routine to determine how much time remains before the driver must respond to a power IRP to prevent a controlled shutdown (a bug check) of the operating system.

The power manager sets a watchdog time-out counter when it issues a power IRP to the device stack. The time-out period for this counter is typically several minutes. If a device in the stack is unresponsive and causes the IRP to stall for the time-out period, the power manager treats this condition as an unrecoverable error and initiates a controlled shutdown of the operating system.

If more than one power watchdog time-out is currently enabled, the routine sets *<i>SecondsRemaining</i> to the time that remains to the next time-out.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 7.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>
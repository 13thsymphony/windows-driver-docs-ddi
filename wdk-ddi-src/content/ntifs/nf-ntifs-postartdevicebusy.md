---
UID: NF:ntifs.PoStartDeviceBusy
title: PoStartDeviceBusy function
author: windows-driver-content
description: The PoStartDeviceBusy routine marks the start of a period of time in which the device is busy.
old-location: kernel\postartdevicebusy.htm
old-project: kernel
ms.assetid: f3801fdf-c300-4863-afb9-49fad011dc4c
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: PoStartDeviceBusy, PoStartDeviceBusy routine [Kernel-Mode Driver Architecture], kernel.postartdevicebusy, portn_b129df72-9d6a-46b7-99db-ad2e96cfeafe.xml, wdm/PoStartDeviceBusy
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	PoStartDeviceBusy
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# PoStartDeviceBusy function
The <b>PoStartDeviceBusy</b> routine marks the start of a period of time in which the device is busy.

## Syntax

````
VOID PoStartDeviceBusy(
  _Inout_ PULONG IdlePointer
);
````

## Parameters

`IdlePointer`

A pointer to an idle counter. This is a pointer value that was previously returned by the <a href="..\wdm\nf-wdm-poregisterdeviceforidledetection.md">PoRegisterDeviceForIdleDetection</a> routine. Because <b>PoRegisterDeviceForIdleDetection</b> might return a <b>NULL</b> pointer, the caller must verify that the pointer is non-<b>NULL</b> before it calls <b>PoStartDeviceBusy</b>.


## Return Value

None

## Remarks

The <b>PoStartDeviceBusy</b> and <a href="..\wdm\nf-wdm-poenddevicebusy.md">PoEndDeviceBusy</a> routines mark the start and end of a time period in which a device is busy. Each call to <b>PoStartDeviceBusy</b> must be followed by a corresponding call to <b>PoEndDeviceBusy</b>.

For each device, the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559829">power manager</a> maintains a count of the number of outstanding <b>PoStartDeviceBusy</b> calls for which it has not yet received a corresponding <b>PoEndDeviceBusy</b> call. A <b>PoStartDeviceBusy</b> call increments the busy count by one. A <b>PoEndDeviceBusy</b> call decrements the busy count by one. A nonzero busy count disables the idle counter for the device. After the busy count reaches zero, the power manager resets the idle counter to the time-out period and enables the counter.

Rather than use the <b>PoStartDeviceBusy</b> and <b>PoEndDeviceBusy</b> routines to reset the idle counter, you can call the <a href="..\wdm\nf-wdm-posetdevicebusyex.md">PoSetDeviceBusyEx</a> routine (or the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559755">PoSetDeviceBusy</a> macro). To disable the idle counter during an extended busy period, a driver can call the <b>PoRegisterDeviceForIdleDetection</b> routine to disable and enable idle notifications at the start and end of the busy period. However, <b>PoStartDeviceBusy</b> and <b>PoEndDeviceBusy</b> are typically more convenient to use for this purpose, and you should consider using these routines in new code that you write for Windows 7 and later versions of Windows.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 7.  |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | Any level |

## See Also

<a href="..\wdm\nf-wdm-poenddevicebusy.md">PoEndDeviceBusy</a>



<a href="..\wdm\nf-wdm-poregisterdeviceforidledetection.md">PoRegisterDeviceForIdleDetection</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559755">PoSetDeviceBusy</a>
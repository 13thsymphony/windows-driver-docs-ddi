---
UID: NF.ntifs.PoStartDeviceBusy
title: PoStartDeviceBusy function
author: windows-driver-content
description: The PoStartDeviceBusy routine marks the start of a period of time in which the device is busy.
old-location: kernel\postartdevicebusy.htm
old-project: kernel
ms.assetid: f3801fdf-c300-4863-afb9-49fad011dc4c
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: PoStartDeviceBusy
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
req.alt-api: PoStartDeviceBusy
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
req.irql: Any level
---

# PoStartDeviceBusy function



## -description
The <b>PoStartDeviceBusy</b> routine marks the start of a period of time in which the device is busy.



## -syntax

````
VOID PoStartDeviceBusy(
  _Inout_ PULONG IdlePointer
);
````


## -parameters

### -param IdlePointer [in, out]

A pointer to an idle counter. This is a pointer value that was previously returned by the <a href="kernel.poregisterdeviceforidledetection">PoRegisterDeviceForIdleDetection</a> routine. Because <b>PoRegisterDeviceForIdleDetection</b> might return a <b>NULL</b> pointer, the caller must verify that the pointer is non-<b>NULL</b> before it calls <b>PoStartDeviceBusy</b>.


## -returns
None


## -remarks
The <b>PoStartDeviceBusy</b> and <a href="kernel.poenddevicebusy">PoEndDeviceBusy</a> routines mark the start and end of a time period in which a device is busy. Each call to <b>PoStartDeviceBusy</b> must be followed by a corresponding call to <b>PoEndDeviceBusy</b>.

For each device, the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559829">power manager</a> maintains a count of the number of outstanding <b>PoStartDeviceBusy</b> calls for which it has not yet received a corresponding <b>PoEndDeviceBusy</b> call. A <b>PoStartDeviceBusy</b> call increments the busy count by one. A <b>PoEndDeviceBusy</b> call decrements the busy count by one. A nonzero busy count disables the idle counter for the device. After the busy count reaches zero, the power manager resets the idle counter to the time-out period and enables the counter.

Rather than use the <b>PoStartDeviceBusy</b> and <b>PoEndDeviceBusy</b> routines to reset the idle counter, you can call the <a href="kernel.posetdevicebusyex">PoSetDeviceBusyEx</a> routine (or the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559755">PoSetDeviceBusy</a> macro). To disable the idle counter during an extended busy period, a driver can call the <b>PoRegisterDeviceForIdleDetection</b> routine to disable and enable idle notifications at the start and end of the busy period. However, <b>PoStartDeviceBusy</b> and <b>PoEndDeviceBusy</b> are typically more convenient to use for this purpose, and you should consider using these routines in new code that you write for Windows 7 and later versions of Windows.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows 7.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
Any level

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.poenddevicebusy">PoEndDeviceBusy</a>
</dt>
<dt>
<a href="kernel.poregisterdeviceforidledetection">PoRegisterDeviceForIdleDetection</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559755">PoSetDeviceBusy</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PoStartDeviceBusy routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


---
UID: NF:wdm.IoRegisterLastChanceShutdownNotification
title: IoRegisterLastChanceShutdownNotification function
author: windows-driver-content
description: The IoRegisterLastChanceShutdownNotification routine registers a driver to receive an IRP_MJ_SHUTDOWN IRP when the system is shut down, after all file systems have been flushed.
old-location: kernel\ioregisterlastchanceshutdownnotification.htm
old-project: kernel
ms.assetid: 9ee590ce-e822-4c15-bb01-6f726268f163
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoRegisterLastChanceShutdownNotification
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows. Not available in Microsoft Windows 98/Me.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoRegisterLastChanceShutdownNotification
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoRegisterLastChanceShutdownNotification function



## -description
The <b>IoRegisterLastChanceShutdownNotification</b> routine registers a driver to receive an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549423">IRP_MJ_SHUTDOWN</a> IRP when the system is shut down, after all file systems have been flushed. 



## -syntax

````
NTSTATUS IoRegisterLastChanceShutdownNotification(
  _In_ PDEVICE_OBJECT DeviceObject
);
````


## -parameters

### -param DeviceObject [in]

Pointer to the device object of the device for which the driver requests shutdown notification. The system passes this pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff543405">DispatchShutdown</a> routine. 


## -returns
<b>IoRegisterLastChanceShutdownNotification</b> returns STATUS_SUCCESS on success, or the appropriate NTSTATUS error code on failure.


## -remarks
The <b>IoRegisterLastChanceShutdownNotification</b> routine registers the driver to receive an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549423">IRP_MJ_SHUTDOWN</a> IRP for the specified device when the system shuts down. The driver receives one such IRP for each device it registers to receive notification for. Drivers handle <b>IRP_MJ_SHUTDOWN</b> IRPs within their <a href="https://msdn.microsoft.com/library/windows/hardware/ff543405">DispatchShutdown</a> routines.

For any device that is registered with this routine, the system sends the <b>IRP_MJ_SHUTDOWN</b> IRP after all file systems are flushed. Only one driver in a device stack should register to receive shutdown notification, by calling either <a href="..\wdm\nf-wdm-ioregistershutdownnotification.md">IoRegisterShutdownNotification</a> or <b>IoRegisterLastChanceShutdownNotification</b>.

If the driver ceases to require shutdown notification for that device, use <a href="..\wdm\nf-wdm-iounregistershutdownnotification.md">IoUnregisterShutdownNotification</a> to remove the driver from the shutdown notification queue.

A driver that calls <b>IoRegisterLastChanceShutdownNotification</b> must satisfy the following restrictions in its <i>DispatchShutdown</i> routine:

The <i>DispatchShutdown</i> routine must not call any pageable routines.

The <i>DispatchShutdown</i> routine must not access pageable memory.

The <i>DispatchShutdown</i> routine must not perform any file I/O operations.

Most drivers that require shutdown notification should call the <a href="..\wdm\nf-wdm-ioregistershutdownnotification.md">IoRegisterShutdownNotification</a> routine, which does not impose these limitations on the <i>DispatchShutdown</i> routine, and which causes the <i>DispatchShutdown</i> routine to be called before the file systems are flushed. Only drivers that must do some cleanup after the file systems are flushed, such as a driver for a mass storage device, should use <b>IoRegisterLastChanceShutdownNotification</b>.

The registered <i>DispatchShutdown</i> routine is called before the power manager sends an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551744">IRP_MN_SET_POWER</a> request for <b>PowerSystemShutdown</b>. The <i>DispatchShutdown</i> routine is not called for transitions to any other power states.


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
Available in Windows 2000 and later versions of Windows. Not available in Microsoft Windows 98/Me.

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
PASSIVE_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh975204">PowerIrpDDis</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh454220">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543405">DispatchShutdown</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-ioregistershutdownnotification.md">IoRegisterShutdownNotification</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iounregistershutdownnotification.md">IoUnregisterShutdownNotification</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoRegisterLastChanceShutdownNotification routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


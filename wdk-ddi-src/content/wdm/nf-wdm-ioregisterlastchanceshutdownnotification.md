---
UID : NF:wdm.IoRegisterLastChanceShutdownNotification
title : IoRegisterLastChanceShutdownNotification function
author : windows-driver-content
description : The IoRegisterLastChanceShutdownNotification routine registers a driver to receive an IRP_MJ_SHUTDOWN IRP when the system is shut down, after all file systems have been flushed.
old-location : kernel\ioregisterlastchanceshutdownnotification.htm
old-project : kernel
ms.assetid : 9ee590ce-e822-4c15-bb01-6f726268f163
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : wdm/IoRegisterLastChanceShutdownNotification, k104_233a75d7-252b-45e3-a980-bda55edd3fdc.xml, IoRegisterLastChanceShutdownNotification routine [Kernel-Mode Driver Architecture], IoRegisterLastChanceShutdownNotification, kernel.ioregisterlastchanceshutdownnotification
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : Available in Windows 2000 and later versions of Windows. Not available in Microsoft Windows 98/Me.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# IoRegisterLastChanceShutdownNotification function
The <b>IoRegisterLastChanceShutdownNotification</b> routine registers a driver to receive an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549423">IRP_MJ_SHUTDOWN</a> IRP when the system is shut down, after all file systems have been flushed.

## Syntax

````
NTSTATUS IoRegisterLastChanceShutdownNotification(
  _In_ PDEVICE_OBJECT DeviceObject
);
````

## Parameters

`DeviceObject`

Pointer to the device object of the device for which the driver requests shutdown notification. The system passes this pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff543405">DispatchShutdown</a> routine.


## Return Value

<b>IoRegisterLastChanceShutdownNotification</b> returns STATUS_SUCCESS on success, or the appropriate NTSTATUS error code on failure.

## Remarks

The <b>IoRegisterLastChanceShutdownNotification</b> routine registers the driver to receive an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549423">IRP_MJ_SHUTDOWN</a> IRP for the specified device when the system shuts down. The driver receives one such IRP for each device it registers to receive notification for. Drivers handle <b>IRP_MJ_SHUTDOWN</b> IRPs within their <a href="https://msdn.microsoft.com/library/windows/hardware/ff543405">DispatchShutdown</a> routines.

For any device that is registered with this routine, the system sends the <b>IRP_MJ_SHUTDOWN</b> IRP after all file systems are flushed. Only one driver in a device stack should register to receive shutdown notification, by calling either <a href="..\wdm\nf-wdm-ioregistershutdownnotification.md">IoRegisterShutdownNotification</a> or <b>IoRegisterLastChanceShutdownNotification</b>.

If the driver ceases to require shutdown notification for that device, use <a href="..\wdm\nf-wdm-iounregistershutdownnotification.md">IoUnregisterShutdownNotification</a> to remove the driver from the shutdown notification queue.

A driver that calls <b>IoRegisterLastChanceShutdownNotification</b> must satisfy the following restrictions in its <i>DispatchShutdown</i> routine:
<ul>
<li>
The <i>DispatchShutdown</i> routine must not call any pageable routines.

</li>
<li>
The <i>DispatchShutdown</i> routine must not access pageable memory.

</li>
<li>
The <i>DispatchShutdown</i> routine must not perform any file I/O operations.

</li>
</ul>Most drivers that require shutdown notification should call the <a href="..\wdm\nf-wdm-ioregistershutdownnotification.md">IoRegisterShutdownNotification</a> routine, which does not impose these limitations on the <i>DispatchShutdown</i> routine, and which causes the <i>DispatchShutdown</i> routine to be called before the file systems are flushed. Only drivers that must do some cleanup after the file systems are flushed, such as a driver for a mass storage device, should use <b>IoRegisterLastChanceShutdownNotification</b>.

The registered <i>DispatchShutdown</i> routine is called before the power manager sends an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551744">IRP_MN_SET_POWER</a> request for <b>PowerSystemShutdown</b>. The <i>DispatchShutdown</i> routine is not called for transitions to any other power states.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | PowerIrpDDis, HwStorPortProhibitedDDIs |

## See Also

<a href="..\wdm\nf-wdm-iounregistershutdownnotification.md">IoUnregisterShutdownNotification</a>

<a href="..\wdm\nf-wdm-ioregistershutdownnotification.md">IoRegisterShutdownNotification</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543405">DispatchShutdown</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoRegisterLastChanceShutdownNotification routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
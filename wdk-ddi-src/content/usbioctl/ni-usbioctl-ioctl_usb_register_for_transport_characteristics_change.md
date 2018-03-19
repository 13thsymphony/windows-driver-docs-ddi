---
UID: NI:usbioctl.IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE
title: IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE
author: windows-driver-content
description: This request registers for notifications about the changes in transport characteristics.
old-location: buses\ioctl_usb_register_for_transport_characteristics_change.htm
old-project: usbref
ms.assetid: 4192501F-5A30-463C-924D-CD4F2C8C3764
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE, IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE control code [Buses], buses.ioctl_usb_register_for_transport_characteristics_change, usbioctl/IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbioctl.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Usbioctl.h
api_name:
-	IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE
product: Windows
targetos: Windows
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_USB_REGISTER_FOR_TRANSPORT_CHARACTERISTICS_CHANGE IOCTL
This request registers for notifications about the changes in transport characteristics.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
<text></text>

### Input Buffer Length
<text></text>

### Output Buffer
<text></text>

### Output Buffer Length
<text></text>

### Input / Output Buffer
The <b>AssociatedIrp.SystemBuffer</b> member is a pointer to a <a href="..\usbioctl\ns-usbioctl-_usb_transport_characteristics_change_registration.md">USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION</a> structure. On input, the client driver can specify the type of notification changes in which the driver is interested by setting the flags in the <b>ChangeNotificationInputFlags</b> member.

On output, the structure is filled with the registration handle and initial values of the transport characteristics.

### Input / Output Buffer Length
The size of the <a href="..\usbioctl\ns-usbioctl-_usb_transport_characteristics_change_registration.md">USB_TRANSPORT_CHARACTERISTICS_CHANGE_REGISTRATION</a> structure.

### Status Block
<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> indicates  the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code.

## Remarks
The transport characteristics of MA-USB mediums can vary significantly over time. If the client diver is interested in knowing the latest information at all times, the driver must register for notification by sending  the request. 

This request can be sent by a user mode application, UMDF driver, or a KMDF driver. USB driver stack checks for stale and bad registration handle. If the request is received on a handle before registration and after unregistration, the driver stack fails the request.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1709 Windows 10, version 1709 |
| **Header** | usbioctl.h |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/usbcon/usb-client-drivers-for-ma-usb">USB client drivers for Media-Agnostic (MA-USB)</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>
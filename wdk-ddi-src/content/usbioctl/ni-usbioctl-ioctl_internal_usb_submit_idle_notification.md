---
UID : NI:usbioctl.IOCTL_INTERNAL_USB_SUBMIT_IDLE_NOTIFICATION
title : IOCTL_INTERNAL_USB_SUBMIT_IDLE_NOTIFICATION
author : windows-driver-content
description : The IOCTL_INTERNAL_USB_SUBMIT_IDLE_NOTIFICATION I/O request is used by drivers to inform the USB bus driver that a device is idle and can be suspended.
old-location : buses\ioctl_internal_usb_submit_idle_notification.htm
old-project : usbref
ms.assetid : e7ce1448-223f-4aea-b5e7-70a3b2f58e77
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : buses.ioctl_internal_usb_submit_idle_notification, IOCTL_INTERNAL_USB_SUBMIT_IDLE_NOTIFICATION control code [Buses], IOCTL_INTERNAL_USB_SUBMIT_IDLE_NOTIFICATION, usbioctl/IOCTL_INTERNAL_USB_SUBMIT_IDLE_NOTIFICATION, usbirp_4a27792b-b726-4741-9d59-5e2b70a3b1c6.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : usbioctl.h
req.include-header : Usbioctl.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : USB_HUB_TYPE
req.product : Windows 10 or later.
---

# IOCTL_INTERNAL_USB_SUBMIT_IDLE_NOTIFICATION IOCTL
The <b>IOCTL_INTERNAL_USB_SUBMIT_IDLE_NOTIFICATION</b> I/O request is used by drivers to inform the USB bus driver that a device is idle and can be suspended. 

When sending this IOCTL, caller must furnish a callback routine that does the actual suspension of the device. The USB bus driver will call this routine at PASSIVE_LEVEL when it is safe for the device to be powered down. If the device supports remote wake up and has no Wait/Wake IRP already pending, the callback routine should submit a Wait/Wake IRP to the bus driver for the device, before powering it down. 

For additional information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563907">Supporting Devices that Have Wake-Up Capabilities</a>


<b>IOCTL_INTERNAL_USB_SUBMIT_IDLE_NOTIFICATION</b> is a kernel-mode I/O control request. This request targets the USB hub PDO. This request must be sent at an IRQL of PASSIVE_LEVEL.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
<b>Parameters.DeviceIoControl.Type3InputBuffer</b> should be a pointer to a <b>USB_IDLE_CALLBACK_INFO</b> structure. This structure should contain a pointer to the callback routine and a pointer to the callback routine context. 

The structure holding the callback information is defined in usbioctl.h as follows:
<pre class="syntax" xml:space="preserve"><code>typedef VOID (*USB_IDLE_CALLBACK)(PVOID Context);

typedef struct _USB_IDLE_CALLBACK_INFO 
{
  USB_IDLE_CALLBACK IdleCallback;
  PVOID IdleContext;
} USB_IDLE_CALLBACK_INFO, *PUSB_IDLE_CALLBACK_INFO;</code></pre>

### Input Buffer Length
The size of a <b>USB_IDLE_CALLBACK_INFO</b> structure.

### Output Buffer
None.

### Output Buffer Length
None.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The bus or port driver sets <b>Irp-&gt;IoStatus.Status</b> to STATUS_SUCCESS or the appropriate error status.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | usbioctl.h (include Usbioctl.h) |
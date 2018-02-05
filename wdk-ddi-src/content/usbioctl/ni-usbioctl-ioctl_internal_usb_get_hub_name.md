---
UID : NI:usbioctl.IOCTL_INTERNAL_USB_GET_HUB_NAME
title : IOCTL_INTERNAL_USB_GET_HUB_NAME
author : windows-driver-content
description : The IOCTL_INTERNAL_USB_GET_HUB_NAME I/O request is used by drivers to retrieve the UNICODE symbolic name for the target PDO if the PDO is for a hub.
old-location : buses\ioctl_internal_usb_get_hub_name.htm
old-project : usbref
ms.assetid : af0a1cfe-16e8-4356-9b5c-2e2523869906
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : buses.ioctl_internal_usb_get_hub_name, IOCTL_INTERNAL_USB_GET_HUB_NAME control code [Buses], IOCTL_INTERNAL_USB_GET_HUB_NAME, usbioctl/IOCTL_INTERNAL_USB_GET_HUB_NAME, usbirp_54327688-c86b-4d05-b81d-5368f694f9ca.xml
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

# IOCTL_INTERNAL_USB_GET_HUB_NAME IOCTL
The <b>IOCTL_INTERNAL_USB_GET_HUB_NAME</b> I/O request is used by drivers to retrieve the UNICODE symbolic name for the target PDO if the PDO is for a hub. Otherwise a <b>NULL</b> string is returned. 

Drivers can use the symbolic name to retrieve additional information about the hub through user-mode I/O control requests and WMI calls.

<b>IOCTL_INTERNAL_USB_GET_HUB_NAME</b> is a kernel-mode I/O control request. This request targets the USB hub PDO. This request must be sent at an IRQL of PASSIVE_LEVEL.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
<b>Irp-&gt;AssociatedIrp.SystemBuffer</b> points to a <a href="..\usbioctl\ns-usbioctl-_usb_hub_name.md">USB_HUB_NAME</a> structure.

### Input Buffer Length
<b>Parameters.DeviceIoControl.OutputBufferLength</b> is the length of the buffer (in bytes) passed in the <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> field.

### Output Buffer
<b>Irp-&gt;AssociatedIrp.SystemBuffer</b> is filled with the root hub's symbolic name.

### Output Buffer Length
The length of the root hub's symbolic name.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
A lower-level driver sets <b>Irp-&gt;IoStatus.Status</b> to STATUS_SUCCESS or the appropriate error status. It will set <b>Irp-&gt;IoStatus.Information</b> to the number of bytes required to hold the USB_ROOT_HUB_NAME structure. If the request fails, the driver can use this information to resubmit the request with a big enough buffer.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | usbioctl.h (include Usbioctl.h) |

## See Also

<a href="..\usbioctl\ns-usbioctl-_usb_root_hub_name.md">USB_ROOT_HUB_NAME</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20IOCTL_INTERNAL_USB_GET_HUB_NAME control code%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
---
UID: NI:usbioctl.IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES
title: IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES
author: windows-driver-content
description: The IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES I/O control request is sent by an application to retrieve information about a specific port on a USB hub.
old-location: buses\ioctl_usb_get_port_connector_properties.htm
old-project: UsbRef
ms.assetid: 23B2A4AF-1255-4332-83A9-EEEB0007B966
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: buses.ioctl_usb_get_port_connector_properties, IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES control code [Buses], IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES, usbioctl/IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: None supported
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Usbioctl.h
apiname:
-	IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES
product: Windows
targetos: Windows
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES IOCTL
The <b>IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES</b> I/O control request is sent by an application to retrieve information about a specific port on a USB hub. 

<b>IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES</b> is a user-mode I/O control request. This request targets the Universal Serial Bus (USB) hub device (GUID_DEVINTERFACE_USB_HUB).

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
<b>AssociatedIrp.SystemBuffer</b> points to a caller-allocated    <a href="..\usbioctl\ns-usbioctl-_usb_port_connector_properties.md">USB_PORT_CONNECTOR_PROPERTIES</a> structure. The caller must set the structure members as follows:<ul>
<li>
The caller must specify the port number of the port being queried in the <b>ConnectionIndex</b> member.  <b>ConnectionIndex</b> must be a value in the range of 1 to <i>n</i>, where <i>n</i> is the highest port number retrieved in a previous <a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_hub_information_ex.md">IOCTL_USB_GET_HUB_INFORMATION_EX</a> I/O control request.

</li>
<li>
The caller must specify the <b>CompanionIndex</b>  member. For a SuperSpeed hub, the caller must set the <b>CompanionIndex</b>  member to 0. 

The caller can use <b>CompanionIndex</b> to get port numbers associated with the port being queried. If more than one companion port is associated with the port, to get all port numbers, the application can send the request in a loop. Start with <b>CompanionIndex</b>  set to 0 and  increment the <b>CompanionIndex</b> value in each iteration until the request completes with <b>CompanionPortNumber</b> set to 0 and <b>CompanionHubSymbolicLinkName</b> is NULL. 

</li>
</ul>

### Input Buffer Length
The <b>Parameters.DeviceIoControl.InputBufferLength</b> member indicates the size, in bytes, of the caller-allocated buffer pointed to by <b>AssociatedIrp.SystemBuffer</b>. For more information see Remarks.

### Output Buffer
On output, <a href="..\usbioctl\ns-usbioctl-_usb_port_connector_properties.md">USB_PORT_CONNECTOR_PROPERTIES</a>, pointed to by  <b>AssociatedIrp.SystemBuffer</b>,  is filled with information about the physical connector associated with the port.

### Output Buffer Length
The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member indicates the size, in bytes, of the output buffer <b>SystemBuffer</b>.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The USB stack sets <b>Irp-&gt;IoStatus.Status</b> to STATUS_SUCCESS if the request is successful. Otherwise, the USB stack sets <b>Status</b> to the appropriate error condition, such as STATUS_INVALID_PARAMETER or STATUS_INSUFFICIENT_RESOURCES. If the hub has not been started or is not functional, the request returns STATUS_UNSUCCESSFUL.

## Remarks
The caller must supply a buffer that is large enough to hold a <a href="..\usbioctl\ns-usbioctl-_usb_port_connector_properties.md">USB_PORT_CONNECTOR_PROPERTIES</a> structure and  the symbolic link name of a companion hub, if such a hub is associated with the specified port. To obtain the size of the buffer to allocate, the caller must send a <b>IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES</b> request. In the request, <b>AssociatedIrp.SystemBuffer</b> must be a caller-allocated <b>USB_PORT_CONNECTOR_PROPERTIES</b> structure and <b>Parameters.DeviceIoControl.InputBufferLength</b> must be  <code>sizeof(USB_PORT_CONNECTOR_PROPERTIES)</code>. Upon successful completion, the <b>ActualLength</b> member of <b>USB_PORT_CONNECTOR_PROPERTIES</b> indicates the actual size of the  buffer. If a symbolic link name exists, the received value includes the size of the string that stores the link name. 

Based on the <b>ActualLength</b> value, the caller can then allocate a buffer and send the  <b>IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES</b> request again. After the request completes, the buffer is filled with port information and the <b>CompanionHubSymbolicLinkName</b> member is a Unicode string that contains the symbolic link  name of the companion hub.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | usbioctl.h (include Usbioctl.h) |

## See Also

<a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_port_connector_properties.md">IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES</a>



<a href="..\usbioctl\ns-usbioctl-_usb_hub_information_ex.md">USB_HUB_INFORMATION_EX</a>



<a href="..\usbioctl\ns-usbioctl-_usb_port_connector_properties.md">USB_PORT_CONNECTOR_PROPERTIES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES control code%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
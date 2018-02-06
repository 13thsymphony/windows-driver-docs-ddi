---
UID: NI:usbioctl.IOCTL_USB_GET_NODE_CONNECTION_ATTRIBUTES
title: IOCTL_USB_GET_NODE_CONNECTION_ATTRIBUTES
author: windows-driver-content
description: The IOCTL_USB_GET_NODE_CONNECTION_ATTRIBUTES I/O control request retrieves the Microsoft-extended port attributes for a specific port.
old-location: buses\ioctl_usb_get_node_connection_attributes.htm
old-project: usbref
ms.assetid: a28613f4-52ba-40f0-9d40-19f1a5d8124a
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: buses.ioctl_usb_get_node_connection_attributes, IOCTL_USB_GET_NODE_CONNECTION_ATTRIBUTES control code [Buses], IOCTL_USB_GET_NODE_CONNECTION_ATTRIBUTES, usbioctl/IOCTL_USB_GET_NODE_CONNECTION_ATTRIBUTES, usbirp_7240de27-e12b-4c72-94c3-5913a217c0c3.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Windows XP, Windows Server 2003, and later.
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
-	IOCTL_USB_GET_NODE_CONNECTION_ATTRIBUTES
product: Windows
targetos: Windows
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_USB_GET_NODE_CONNECTION_ATTRIBUTES IOCTL
The <b>IOCTL_USB_GET_NODE_CONNECTION_ATTRIBUTES</b> I/O control request retrieves the Microsoft-extended port attributes for a specific port. 

<b>IOCTL_USB_GET_NODE_CONNECTION_ATTRIBUTES</b> is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB).

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The <b>AssociatedIrp.SystemBuffer</b> member points to a user-allocated <a href="..\usbioctl\ns-usbioctl-_usb_node_connection_attributes.md">USB_NODE_CONNECTION_ATTRIBUTES</a> structure. On input, the caller specifies the port number in the <b>ConnectionIndex</b> member of a <b>USB_NODE_CONNECTION_ATTRIBUTES</b> structure.

### Input Buffer Length
The size of a <a href="..\usbioctl\ns-usbioctl-_usb_node_connection_attributes.md">USB_NODE_CONNECTION_ATTRIBUTES</a> structure.

### Output Buffer
On output, the <a href="..\usbioctl\ns-usbioctl-_usb_node_connection_attributes.md">USB_NODE_CONNECTION_ATTRIBUTES</a> structure at <b>AssociatedIrp.SystemBuffer</b> describes the Microsoft-extended port attributes for the port. <b>Note</b>  For Windows Vista, Windows Server 2008, and Windows 7, the Microsoft-extended port attributes field is set to  zero.  <p class="note">For Windows XP and Windows Server 2003, the Microsoft-extended port attribute might be set to USB_PORTATTR_NO_OVERCURRENT_UI. This value indicates that user interface will be hidden when an overcurrent occurs on the port.

### Output Buffer Length
<b>Parameters.DeviceIoControl.OutputBufferLength</b> indicates the size, in bytes, of the data returned at <b>SystemBuffer</b>.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The USB stack sets <b>Irp-&gt;IoStatus.Status</b> to STATUS_SUCCESS if the request is successful. Otherwise, the USB stack sets <b>Status</b> to the appropriate error condition, such as STATUS_INVALID_PARAMETER or STATUS_INSUFFICIENT_RESOURCES. If the hub has not been started or is not functional, the request returns STATUS_UNSUCCESSFUL.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP, Windows Server 2003, and later. Windows XP, Windows Server 2003, and later. |
| **Header** | usbioctl.h (include Usbioctl.h) |

## See Also

<a href="..\usbioctl\ns-usbioctl-_usb_node_connection_attributes.md">USB_NODE_CONNECTION_ATTRIBUTES</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20IOCTL_USB_GET_NODE_CONNECTION_ATTRIBUTES control code%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
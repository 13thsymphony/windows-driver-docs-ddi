---
UID: NI:usbioctl.IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION
title: IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION
author: windows-driver-content
description: The IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION I/O control request retrieves one or more descriptors for the device that is associated with the indicated port index.IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION is a user-mode I/O control request.
old-location: buses\ioctl_usb_get_descriptor_from_node_connection.htm
old-project: usbref
ms.assetid: 60b41f73-ef12-4d3f-9df4-8958ab66bf14
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: buses.ioctl_usb_get_descriptor_from_node_connection, IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION control code [Buses], IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION, usbioctl/IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION, usbirp_060f6333-3fe9-4a4b-8ff1-f7403a3e8dfe.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION
product: Windows
targetos: Windows
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION IOCTL
The <b>IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION</b> I/O control request retrieves one or more descriptors for the device that is associated with the indicated port index.

<b>IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION</b> is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB).

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The <b>AssociatedIrp.SystemBuffer</b> member points to a <a href="..\usbioctl\ns-usbioctl-_usb_descriptor_request.md">USB_DESCRIPTOR_REQUEST</a> structure that describes the descriptor request.

### Input Buffer Length
The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member indicates the size, in bytes, of the user-allocated output buffer in the <b>Data</b> member of the <a href="..\usbioctl\ns-usbioctl-_usb_descriptor_request.md">USB_DESCRIPTOR_REQUEST</a> structure.

### Output Buffer
The <b>Data</b> member of the <a href="..\usbioctl\ns-usbioctl-_usb_descriptor_request.md">USB_DESCRIPTOR_REQUEST</a> structure at <b>AssociatedIrp.SystemBuffer</b> points to the output buffer.

### Output Buffer Length
<text></text>

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The USB stack sets <b>Irp-&gt;IoStatus.Status</b> to STATUS_SUCCESS if the request is successful. Otherwise, the USB stack sets <b>Status</b> to the appropriate error condition, such as STATUS_INVALID_PARAMETER or STATUS_INSUFFICIENT_RESOURCES.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | usbioctl.h (include Usbioctl.h) |

## See Also

<a href="..\usbioctl\ns-usbioctl-_usb_descriptor_request.md">USB_DESCRIPTOR_REQUEST</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION control code%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
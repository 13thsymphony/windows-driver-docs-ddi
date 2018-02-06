---
UID: NS:usb._URB_SELECT_INTERFACE
title: "_URB_SELECT_INTERFACE"
author: windows-driver-content
description: The _URB_SELECT_INTERFACE structure is used by USB client drivers to select an alternate setting for an interface or to change the maximum packet size of a pipe in the current configuration on a USB device.
old-location: buses\_urb_select_interface.htm
old-project: usbref
ms.assetid: 48f80c80-49af-4cda-961b-8967e8d4897a
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: usb/_URB_SELECT_INTERFACE, buses._urb_select_interface, usbstrct_c23c108d-422b-4dee-a1de-a5e341fc1800.xml, _URB_SELECT_INTERFACE structure [Buses], _URB_SELECT_INTERFACE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usb.h
req.include-header: Usb.h
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
-	usb.h
apiname:
-	_URB_SELECT_INTERFACE
product: Windows
targetos: Windows
req.typenames: 
req.product: Windows 10 or later.
---

# _URB_SELECT_INTERFACE structure
The <b>_URB_SELECT_INTERFACE</b> structure is used by USB client drivers to select an alternate setting for an interface or to change the maximum packet size of a pipe in the current configuration on a USB device.

## Syntax
````
struct _URB_SELECT_INTERFACE {
  struct URB_HEADER  Hdr;
  USBD_CONFIGURATION_HANDLE  ConfigurationHandle;
  USBD_INTERFACE_INFORMATION Interface;
};
````

## Members


`_URB_HEADER`



`ConfigurationHandle`

Specifies the handle to the configuration that this interface belongs to. The host controller driver returns this handle when the client selects the configuration with an URB_FUNCTION_SELECT_CONFIGURATION request.

`Hdr`

Pointer to a <a href="..\usb\ns-usb-_urb_header.md">_URB_HEADER</a> structure that specifies the URB header information. <b>Hdr.Function</b> must be URB_FUNCTION_SELECT_INTERFACE, and <b>Hdr.Length</b> must be the size of the entire URB.

`Interface`

A variable-length <a href="..\usb\ns-usb-_usbd_interface_information.md">USBD_INTERFACE_INFORMATION</a> structure that specifies the interface and the new alternate setting for that interface, and if required, the new maximum packet sizes for the corresponding pipes. For more information, see Remarks.

## Remarks
You can use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537164">GET_SELECT_INTERFACE_REQUEST_SIZE</a> macro to determine the size of the URB_FUNCTION_SELECT_INTERFACE URB, and the <b>UsbBuildSelectInterfaceRequest</b> routine to format the URB.

The <a href="..\usb\ns-usb-_usbd_interface_information.md">USBD_INTERFACE_INFORMATION</a> structure contains information about the interface and its alternate setting.  The <b>Pipes</b> member of <b>USBD_INTERFACE_INFORMATION</b> points to an array of <a href="..\usb\ns-usb-_usbd_pipe_information.md">USBD_PIPE_INFORMATION</a> structures. The array stores information about the  pipes associated with the endpoints of the interface. You can override certain default settings for a pipe, such as its maximum packet size. To alter the maximum packet size, set the USBD_PF_CHANGE_MAX_PACKET flag in <code>Pipes[i].PipeFlags</code>, and then specify the new value in <code>Pipes[i].MaximumPacketSize</code>. 

 After the bus driver successfully completes processing the URB_FUNCTION_SELECT_INTERFACE URB, it returns an array of handles for each pipe in the  <code>Pipes[i].PipeHandle</code>  member. The client driver can store pipe handles to send I/O requests to specific pipes.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | usb.h (include Usb.h) |

## See Also

<a href="..\usb\ns-usb-_usbd_interface_information.md">USBD_INTERFACE_INFORMATION</a>

<a href="https://msdn.microsoft.com/710b4f96-eeee-4313-b068-b2f2e718f8d2">Configuring USB Devices</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>

<a href="..\usb\ns-usb-_urb_header.md">_URB_HEADER</a>

<a href="..\usb\ns-usb-_urb.md">URB</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20_URB_SELECT_INTERFACE structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
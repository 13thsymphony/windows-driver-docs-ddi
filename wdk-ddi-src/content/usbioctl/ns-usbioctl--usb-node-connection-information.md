---
UID: NS.usbioctl._USB_NODE_CONNECTION_INFORMATION
title: USB_NODE_CONNECTION_INFORMATION
author: windows-driver-content
description: The USB_NODE_CONNECTION_INFORMATION structure is used with the IOCTL_USB_GET_NODE_CONNECTION_INFORMATION request to retrieve information about a USB port and connected device.
old-location: buses\usb_node_connection_information.htm
old-project: usbref
ms.assetid: 1ed92343-c830-4e5e-a2f8-30b20057b1f0
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: USB_NODE_CONNECTION_INFORMATION, USB_NODE_CONNECTION_INFORMATION, *PUSB_NODE_CONNECTION_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: USB_NODE_CONNECTION_INFORMATION
req.alt-loc: usbioctl.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# USB_NODE_CONNECTION_INFORMATION structure



## -description
<p>The <b>USB_NODE_CONNECTION_INFORMATION</b> structure is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537319">IOCTL_USB_GET_NODE_CONNECTION_INFORMATION</a>  request to retrieve information about a USB port and connected device.</p>


## -syntax

````
typedef struct _USB_NODE_CONNECTION_INFORMATION {
  ULONG                 ConnectionIndex;
  USB_DEVICE_DESCRIPTOR DeviceDescriptor;
  UCHAR                 CurrentConfigurationValue;
  BOOLEAN               LowSpeed;
  BOOLEAN               DeviceIsHub;
  USHORT                DeviceAddress;
  ULONG                 NumberOfOpenPipes;
  USB_CONNECTION_STATUS ConnectionStatus;
  USB_PIPE_INFO         PipeList[];
} USB_NODE_CONNECTION_INFORMATION, *PUSB_NODE_CONNECTION_INFORMATION;
````


## -struct-fields
<dl>

### -field <b>ConnectionIndex</b>

<dd>
<p>A value that is greater than or equal to 1 that specifies the number of the port.</p>
</dd>

### -field <b>DeviceDescriptor</b>

<dd>
<p>A <a href="https://msdn.microsoft.com/library/windows/hardware/ff539280">USB_DEVICE_DESCRIPTOR</a> structure that reports the USB device descriptor that is returned by the attached device during enumeration.</p>
</dd>

### -field <b>CurrentConfigurationValue</b>

<dd>
<p>The value that is used with the SetConfiguration request to specify that current configuration of the device that is connected to the indicated port. For more information about this member, see Universal Serial Bus Specification.</p>
</dd>

### -field <b>LowSpeed</b>

<dd>
<p>A Boolean value that indicates whether the port and its connected device are operating at low speed. <b>TRUE</b> indicates that the port and its connected device are currently operating at a low speed. <b>FALSE</b> indicates otherwise.</p>
</dd>

### -field <b>DeviceIsHub</b>

<dd>
<p>A Boolean value that indicates if the device that is attached to the port is a hub. If <b>TRUE</b>, the device that is attached to the port is a hub. If <b>FALSE</b>, the device is not a hub.</p>
</dd>

### -field <b>DeviceAddress</b>

<dd>
<p>The USB-assigned, bus-relative address of the device that is attached to the port.</p>
</dd>

### -field <b>NumberOfOpenPipes</b>

<dd>
<p>The number of open USB pipes that are associated with the port.</p>
</dd>

### -field <b>ConnectionStatus</b>

<dd>
<p>A <a href="https://msdn.microsoft.com/library/windows/hardware/ff539247">USB_CONNECTION_STATUS</a>-typed enumerator that indicates the connection status.</p>
</dd>

### -field <b>PipeList</b>

<dd>
<p>An array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff540118">USB_PIPE_INFO</a> structures  that describes the open pipes that are associated with the port. Pipe descriptions include the schedule offset of the pipe and the associated endpoint descriptor. This information can be used to calculate bandwidth usage.</p>
</dd>
</dl>

## -remarks
<p>If there is no device connected to the USB port, <a href="https://msdn.microsoft.com/library/windows/hardware/ff537319">IOCTL_USB_GET_NODE_CONNECTION_INFORMATION</a> returns only information about the port. If a device is connected to the port, <b>IOCTL_USB_GET_NODE_CONNECTION_INFORMATION</b> returns information about both the port and the connected device.</p>

<p>The <a href="https://msdn.microsoft.com/library/windows/hardware/ff540094">USB_NODE_CONNECTION_INFORMATION_EX</a> structure is an extended version of <b>USB_NODE_CONNECTION_INFORMATION</b>. The two structures are identical, except for one member. In <b>USB_NODE_CONNECTION_INFORMATION_EX</b>, the <b>LowSpeed</b> member is replaced by the <b>Speed</b> member. <b>LowSpeed</b> is a Boolean value, so when it is <b>TRUE</b>, the device is low speed. When it is <b>FALSE</b>, the device is high speed or full speed. Thus the <b>USB_NODE_CONNECTION_INFORMATION</b> structure cannot differentiate between high and full speeds. </p>

<p>The <b>Speed</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540094">USB_NODE_CONNECTION_INFORMATION_EX</a> structure is a UCHAR and it can specify any of the values of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539294">USB_DEVICE_SPEED</a> enumerator.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Usbioctl.h (include Usbioctl.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537319">IOCTL_USB_GET_NODE_CONNECTION_INFORMATION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537321">IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539247">USB_CONNECTION_STATUS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539280">USB_DEVICE_DESCRIPTOR</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539294">USB_DEVICE_SPEED</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540094">USB_NODE_CONNECTION_INFORMATION_EX</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540118">USB_PIPE_INFO</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_NODE_CONNECTION_INFORMATION structure%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

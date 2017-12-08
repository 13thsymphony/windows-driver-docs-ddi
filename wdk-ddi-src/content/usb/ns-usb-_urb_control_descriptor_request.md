---
UID: NS.USB._URB_CONTROL_DESCRIPTOR_REQUEST
title: _URB_CONTROL_DESCRIPTOR_REQUEST
author: windows-driver-content
description: The _URB_CONTROL_DESCRIPTOR_REQUEST structure is used by USB client drivers to get or set descriptors on a USB device.
old-location: buses\_urb_control_descriptor_request.htm
old-project: usbref
ms.assetid: 770659f4-701f-47dc-b20f-e51c85cdee4b
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _URB_CONTROL_DESCRIPTOR_REQUEST,
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
req.alt-api: _URB_CONTROL_DESCRIPTOR_REQUEST
req.alt-loc: usb.h
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
req.product: Windows 10 or later.
---

# _URB_CONTROL_DESCRIPTOR_REQUEST structure



## -description
The <b>_URB_CONTROL_DESCRIPTOR_REQUEST</b> structure is used by USB client drivers to get or set descriptors on a USB device.


## -syntax

````
struct _URB_CONTROL_DESCRIPTOR_REQUEST {
  struct URB_HEADER  Hdr;
  PVOID               Reserved;
  ULONG               Reserved0;
  ULONG               TransferBufferLength;
  PVOID               TransferBuffer;
  PMDL                TransferBufferMDL;
  struct URB  *UrbLink;
  struct URB_HCD_AREA  hca;
  USHORT              Reserved1;
  UCHAR               Index;
  UCHAR               DescriptorType;
  USHORT              LanguageId;
  USHORT              Reserved2;
};
````


## -struct-fields

### -field Hdr

Pointer to a <a href="..\usb\ns-usb-_urb_header.md">_URB_HEADER</a> structure that specifies the URB header information. <b>Hdr.Function</b> must be one of the following:
<dl>
<dd>URB_FUNCTION_GET_DESCRIPTOR_FROM_DEVICE</dd>
<dd>URB_FUNCTION_GET_DESCRIPTOR_FROM_ENDPOINT</dd>
<dd>URB_FUNCTION_GET_DESCRIPTOR_FROM_INTERFACE</dd>
<dd>URB_FUNCTION_SET_DESCRIPTOR_TO_DEVICE</dd>
<dd>URB_FUNCTION_SET_DESCRIPTOR_TO_ENDPOINT</dd>
<dd>URB_FUNCTION_SET_DESCRIPTOR_TO_INTERFACE</dd>
</dl>
<b>Hdr.Length</b> must equal <code>sizeof(_URB_CONTROL_DESCRIPTOR_REQUEST)</code>.

### -field Reserved

Reserved. Do not use.

### -field Reserved0

Reserved. Do not use.

### -field TransferBufferLength

Specifies the length, in bytes, of the buffer specified in <b>TransferBuffer</b> or described in <b>TransferBufferMDL</b>. The host controller driver returns the number of bytes sent to or read from the pipe in this member.

### -field TransferBuffer

Pointer to a resident buffer for the transfer or is <b>NULL</b> if an MDL is supplied in <b>TransferBufferMDL</b>.

### -field TransferBufferMDL

Pointer to an MDL that describes a resident buffer or is <b>NULL</b> if a buffer is supplied in <b>TransferBuffer</b>. This MDL must be allocated from nonpaged pool.

### -field UrbLink

Reserved. Do not use.

### -field hca

Reserved. Do not use.

### -field Reserved1

Reserved. Do not use.

### -field Index

Specifies the device-defined index of the descriptor that is being retrieved or set.

### -field DescriptorType

Indicates what type of descriptor is being retrieved or set. One of the following values must be specified:
<dl>
<dd>USB_DEVICE_DESCRIPTOR_TYPE</dd>
<dd>USB_CONFIGURATION_DESCRIPTOR_TYPE</dd>
<dd>USB_STRING_DESCRIPTOR_TYPE</dd>
</dl>

### -field LanguageId

Specifies the language ID of the descriptor to be retrieved when USB_STRING_DESCRIPTOR_TYPE is set in <b>DescriptorType</b>. This member must be set to zero for any other value in <b>DescriptorType</b>.

### -field Reserved2

Reserved. Do not use.

## -remarks
Drivers can use the <b>UsbBuildGetDescriptorRequest</b> service routine to format this URB. If the caller passes a buffer too small to hold all of the data, the bus driver truncates the data to fit in the buffer without error.

When the caller requests the device descriptor, the bus driver returns a <a href="buses.usb_device_descriptor">USB_DEVICE_DESCRIPTOR</a> data structure.

When the caller requests a configuration descriptor, the bus driver returns the configuration descriptor in a <a href="buses.usb_configuration_descriptor">USB_CONFIGURATION_DESCRIPTOR</a> structure, followed by the interface and endpoint descriptors for that configuration. The driver can access the interface and endpoint descriptors as <a href="buses.usb_interface_descriptor">USB_INTERFACE_DESCRIPTOR</a> and <a href="buses.usb_endpoint_descriptor">USB_ENDPOINT_DESCRIPTOR</a> structures. The bus driver also returns any class-specific or device-specific descriptors. The system provides the <a href="buses.usbd_parseconfigurationdescriptorex">USBD_ParseConfigurationDescriptorEx</a> and <a href="buses.usbd_parsedescriptors">USBD_ParseDescriptors</a> service routines to find individual descriptors within the buffer.

When the caller requests a string descriptor, the bus driver returns a <a href="buses.usb_string_descriptor">USB_STRING_DESCRIPTOR</a> structure. The string itself is found in the variable-length <b>bString</b> member of the string descriptor.

The reserved members of this structure must be treated as opaque and are reserved for system use.

## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Usb.h (include Usb.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="buses.urb">URB</a>
</dt>
<dt>
<a href="..\usb\ns-usb-_urb_header.md">_URB_HEADER</a>
</dt>
<dt>
<a href="buses.usb_configuration_descriptor">USB_CONFIGURATION_DESCRIPTOR</a>
</dt>
<dt>
<a href="buses.usb_device_descriptor">USB_DEVICE_DESCRIPTOR</a>
</dt>
<dt>
<a href="buses.usb_endpoint_descriptor">USB_ENDPOINT_DESCRIPTOR</a>
</dt>
<dt>
<a href="buses.usb_interface_descriptor">USB_INTERFACE_DESCRIPTOR</a>
</dt>
<dt>
<a href="buses.usb_string_descriptor">USB_STRING_DESCRIPTOR</a>
</dt>
<dt>
<a href="buses.usb_structures_and_enumerations">USB Structures</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20_URB_CONTROL_DESCRIPTOR_REQUEST structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

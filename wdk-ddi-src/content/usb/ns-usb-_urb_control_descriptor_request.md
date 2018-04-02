---
UID: NS:usb._URB_CONTROL_DESCRIPTOR_REQUEST
title: "_URB_CONTROL_DESCRIPTOR_REQUEST"
author: windows-driver-content
description: The _URB_CONTROL_DESCRIPTOR_REQUEST structure is used by USB client drivers to get or set descriptors on a USB device.
old-location: buses\_urb_control_descriptor_request.htm
old-project: usbref
ms.assetid: 770659f4-701f-47dc-b20f-e51c85cdee4b
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "_URB_CONTROL_DESCRIPTOR_REQUEST, _URB_CONTROL_DESCRIPTOR_REQUEST structure [Buses], buses._urb_control_descriptor_request, usb/_URB_CONTROL_DESCRIPTOR_REQUEST, usbstrct_f28020e9-3fa4-466c-8cc5-5630d3b06d9c.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usb.h
api_name:
-	_URB_CONTROL_DESCRIPTOR_REQUEST
product: Windows
targetos: Windows
req.typenames: 
req.product: Windows 10 or later.
---

# _URB_CONTROL_DESCRIPTOR_REQUEST structure
The <b>_URB_CONTROL_DESCRIPTOR_REQUEST</b> structure is used by USB client drivers to get or set descriptors on a USB device.

## Syntax
```
struct _URB_CONTROL_DESCRIPTOR_REQUEST {
  _URB_HEADER   Hdr;
  struct        _URB_HEADER;
  PVOID         Reserved;
  ULONG         Reserved0;
  ULONG         TransferBufferLength;
  PVOID         TransferBuffer;
  PMDL          TransferBufferMDL;
  _URB          *UrbLink;
  struct        _URB;
  _URB_HCD_AREA hca;
  struct        _URB_HCD_AREA;
  USHORT        Reserved1;
  UCHAR         Index;
  UCHAR         DescriptorType;
  USHORT        LanguageId;
  USHORT        Reserved2;
};
```

## Members


`Hdr`

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540409">_URB_HEADER</a> structure that specifies the URB header information. <b>Hdr.Function</b> must be one of the following:

<b>Hdr.Length</b> must equal <code>sizeof(_URB_CONTROL_DESCRIPTOR_REQUEST)</code>.

`Reserved`

Reserved. Do not use.

`Reserved0`

Reserved. Do not use.

`TransferBufferLength`

Specifies the length, in bytes, of the buffer specified in <b>TransferBuffer</b> or described in <b>TransferBufferMDL</b>. The host controller driver returns the number of bytes sent to or read from the pipe in this member.

`TransferBuffer`

Pointer to a resident buffer for the transfer or is <b>NULL</b> if an MDL is supplied in <b>TransferBufferMDL</b>.

`TransferBufferMDL`

Pointer to an MDL that describes a resident buffer or is <b>NULL</b> if a buffer is supplied in <b>TransferBuffer</b>. This MDL must be allocated from nonpaged pool.

`UrbLink`

Reserved. Do not use.

`hca`

Reserved. Do not use.

`Reserved1`

Reserved. Do not use.

`Index`

Specifies the device-defined index of the descriptor that is being retrieved or set.

`DescriptorType`

Indicates what type of descriptor is being retrieved or set. One of the following values must be specified:

`LanguageId`

Specifies the language ID of the descriptor to be retrieved when USB_STRING_DESCRIPTOR_TYPE is set in <b>DescriptorType</b>. This member must be set to zero for any other value in <b>DescriptorType</b>.

`Reserved2`

Reserved. Do not use.

## Remarks
Drivers can use the <b>UsbBuildGetDescriptorRequest</b> service routine to format this URB. If the caller passes a buffer too small to hold all of the data, the bus driver truncates the data to fit in the buffer without error.

When the caller requests the device descriptor, the bus driver returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff539280">USB_DEVICE_DESCRIPTOR</a> data structure.

When the caller requests a configuration descriptor, the bus driver returns the configuration descriptor in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff539241">USB_CONFIGURATION_DESCRIPTOR</a> structure, followed by the interface and endpoint descriptors for that configuration. The driver can access the interface and endpoint descriptors as <a href="https://msdn.microsoft.com/library/windows/hardware/ff540065">USB_INTERFACE_DESCRIPTOR</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff539317">USB_ENDPOINT_DESCRIPTOR</a> structures. The bus driver also returns any class-specific or device-specific descriptors. The system provides the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539102">USBD_ParseConfigurationDescriptorEx</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff539109">USBD_ParseDescriptors</a> service routines to find individual descriptors within the buffer.

When the caller requests a string descriptor, the bus driver returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540147">USB_STRING_DESCRIPTOR</a> structure. The string itself is found in the variable-length <b>bString</b> member of the string descriptor.

The reserved members of this structure must be treated as opaque and are reserved for system use.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | usb.h (include Usb.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539241">USB_CONFIGURATION_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539280">USB_DEVICE_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539317">USB_ENDPOINT_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540065">USB_INTERFACE_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540147">USB_STRING_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540409">_URB_HEADER</a>
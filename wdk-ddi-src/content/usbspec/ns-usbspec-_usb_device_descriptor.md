---
UID: NS.USBSPEC._USB_DEVICE_DESCRIPTOR
title: _USB_DEVICE_DESCRIPTOR
author: windows-driver-content
description: The USB_DEVICE_DESCRIPTOR structure is used by USB client drivers to retrieve a USB-defined device descriptor.
old-location: buses\usb_device_descriptor.htm
old-project: usbref
ms.assetid: 124184ef-7410-4e04-abb2-e07db4ae2cbf
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _USB_DEVICE_DESCRIPTOR, *PUSB_DEVICE_DESCRIPTOR, USB_DEVICE_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbspec.h
req.include-header: Usb100.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: USB_DEVICE_DESCRIPTOR
req.alt-loc: usbspec.h
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

# _USB_DEVICE_DESCRIPTOR structure



## -description
The <b>USB_DEVICE_DESCRIPTOR</b> structure is used by USB client drivers to retrieve a USB-defined device descriptor.


## -syntax

````
typedef struct _USB_DEVICE_DESCRIPTOR {
  UCHAR  bLength;
  UCHAR  bDescriptorType;
  USHORT bcdUSB;
  UCHAR  bDeviceClass;
  UCHAR  bDeviceSubClass;
  UCHAR  bDeviceProtocol;
  UCHAR  bMaxPacketSize0;
  USHORT idVendor;
  USHORT idProduct;
  USHORT bcdDevice;
  UCHAR  iManufacturer;
  UCHAR  iProduct;
  UCHAR  iSerialNumber;
  UCHAR  bNumConfigurations;
} USB_DEVICE_DESCRIPTOR, *PUSB_DEVICE_DESCRIPTOR;
````


## -struct-fields

### -field bLength

Specifies the length, in bytes, of this descriptor.

### -field bDescriptorType

Specifies the descriptor type. Must be set to <b>USB_DEVICE_DESCRIPTOR_TYPE</b>.

### -field bcdUSB

Identifies the version of the USB specification that this descriptor structure complies with. This value is a binary-coded decimal number.

### -field bDeviceClass

Specifies the class code of the device as assigned by the USB specification group.

### -field bDeviceSubClass

Specifies the subclass code of the device as assigned by the USB specification group.

### -field bDeviceProtocol

Specifies the protocol code of the device as assigned by the USB specification group.

### -field bMaxPacketSize0

Specifies the maximum packet size, in bytes, for endpoint zero of the device. The value must be set to 8, 16, 32, or 64.

### -field idVendor

Specifies the vendor identifier for the device as assigned by the USB specification committee.

### -field idProduct

Specifies the product identifier. This value is assigned by the manufacturer and is device-specific.

### -field bcdDevice

Identifies the version of the device. This value is a binary-coded decimal number.

### -field iManufacturer

Specifies a device-defined index of the string descriptor that provides a string containing the name of the manufacturer of this device.

### -field iProduct

Specifies a device-defined index of the string descriptor that provides a string that contains a description of the device.

### -field iSerialNumber

Specifies a device-defined index of the string descriptor that provides a string that contains a manufacturer-determined serial number for the device.

### -field bNumConfigurations

Specifies the total number of possible configurations for the device.

## -remarks
This structure is used to hold a retrieved USB-defined device descriptor. This information can then be used to further configure or retrieve information about the device. Device descriptors are retrieved by submitting a get-descriptor URB.

The <b>iManufacturer</b>, <b>iProduct</b>, and <b>iSerialNumber</b> values, when returned from the host controller driver, contain index values into an array of string descriptors maintained by the device. To retrieve these strings, a string descriptor request can be sent to the device using these index values.

## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Usbspec.h (include Usb100.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff538943">UsbBuildGetDescriptorRequest</a>
</dt>
<dt>
<a href="..\usb\ns-usb-_urb_control_descriptor_request.md">_URB_CONTROL_DESCRIPTOR_REQUEST</a>
</dt>
<dt>
<a href="buses.usb_structures_and_enumerations">USB Structures</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_DEVICE_DESCRIPTOR structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

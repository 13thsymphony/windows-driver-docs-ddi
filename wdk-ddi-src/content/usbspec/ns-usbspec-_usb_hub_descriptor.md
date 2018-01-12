---
UID: NS:usbspec._USB_HUB_DESCRIPTOR
title: _USB_HUB_DESCRIPTOR
author: windows-driver-content
description: The USB_HUB_DESCRIPTOR structure contains a hub descriptor.
old-location: buses\usb_hub_descriptor.htm
old-project: usbref
ms.assetid: 6f5521f4-44da-4470-b649-d98c1d4e4891
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _USB_HUB_DESCRIPTOR, USB_HUB_DESCRIPTOR, *PUSB_HUB_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbspec.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: USB_HUB_DESCRIPTOR
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
req.typenames: USB_HUB_DESCRIPTOR, *PUSB_HUB_DESCRIPTOR
req.product: Windows 10 or later.
---

# _USB_HUB_DESCRIPTOR structure



## -description
The <b>USB_HUB_DESCRIPTOR</b> structure contains a hub descriptor.



## -syntax

````
typedef struct _USB_HUB_DESCRIPTOR {
  UCHAR  bDescriptorLength;
  UCHAR  bDescriptorType;
  UCHAR  bNumberOfPorts;
  USHORT wHubCharacteristics;
  UCHAR  bPowerOnToPowerGood;
  UCHAR  bHubControlCurrent;
  UCHAR  bRemoveAndPowerMask[64];
} USB_HUB_DESCRIPTOR, *PUSB_HUB_DESCRIPTOR;
````


## -struct-fields

### -field bDescriptorLength

The length, in bytes, of the descriptor.


### -field bDescriptorType

The descriptor type. For hub descriptors, this value should be 0x29.


### -field bNumberOfPorts

The number of ports on the hub.


### -field wHubCharacteristics

The hub characteristics. For more information about this member, see Universal Serial Bus Specification.


### -field bPowerOnToPowerGood

The time, in 2-millisecond intervals, that it takes the device to turn on completely. For more information about this member, see Universal Serial Bus Specification.


### -field bHubControlCurrent

The maximum current requirements, in milliamperes, of the controller component of the hub.


### -field bRemoveAndPowerMask

Not currently implemented. Do not use this member. 

This member implements DeviceRemovable and PortPwrCtrlMask fields of the hub descriptor. For more information about these fields, see Universal Serial Bus Specification. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Usbspec.h (include Usbioctl.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\usbioctl\ns-usbioctl-_usb_hub_information.md">USB_HUB_INFORMATION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_HUB_DESCRIPTOR structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


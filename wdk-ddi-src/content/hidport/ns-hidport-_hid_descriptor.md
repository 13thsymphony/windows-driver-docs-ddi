---
UID: NS.HIDPORT._HID_DESCRIPTOR
title: _HID_DESCRIPTOR
author: windows-driver-content
description: The HID_DESCRIPTOR structure represents a HID descriptor for a HIDClass device.
old-location: hid\hid_descriptor.htm
old-project: hid
ms.assetid: 80a6a5d8-b13a-418d-a4bd-941d3a913c1e
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _HID_DESCRIPTOR, *PHID_DESCRIPTOR, HID_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hidport.h
req.include-header: Hidport.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HID_DESCRIPTOR
req.alt-loc: hidport.h
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
---

# _HID_DESCRIPTOR structure



## -description
The HID_DESCRIPTOR structure represents a HID descriptor for a HIDClass device.



## -syntax

````
typedef struct _HID_DESCRIPTOR {
  UCHAR  bLength;
  UCHAR  bDescriptorType;
  USHORT bcdHID;
  UCHAR  bCountry;
  UCHAR  bNumDescriptors;
  struct {
    UCHAR  bReportType;
    USHORT wReportLength;
  } DescriptorList [1];
} HID_DESCRIPTOR, *PHID_DESCRIPTOR;
````


## -struct-fields

### -field bLength


### -field bDescriptorType


### -field bcdHID


### -field bCountry


### -field bNumDescriptors


### -field DescriptorList [1]


## -remarks
The HID class driver uses an <a href="..\hidport\ni-hidport-ioctl_hid_get_device_descriptor.md">IOCTL_HID_GET_DEVICE_DESCRIPTOR</a> request to obtain a device's HID descriptor from a HID minidriver.

For information about HID descriptors, see the Universal Serial Bus (USB) standard<i> Device Class Definition for Human Interface Devices (HID)</i> located at the <a href="http://www.usb.org/home">USB Implementers Forum website</a>.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Hidport.h (include Hidport.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\hidport\ni-hidport-ioctl_hid_get_device_descriptor.md">IOCTL_HID_GET_DEVICE_DESCRIPTOR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HID_DESCRIPTOR structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


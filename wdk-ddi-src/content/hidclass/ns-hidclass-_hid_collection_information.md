---
UID: NS.HIDCLASS._HID_COLLECTION_INFORMATION
title: _HID_COLLECTION_INFORMATION
author: windows-driver-content
description: The HID_COLLECTION_INFORMATION structure contains general information about a top-level collection.
old-location: hid\hid_collection_information.htm
old-project: hid
ms.assetid: 47490858-3fe0-4a94-adae-6589cad6a842
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _HID_COLLECTION_INFORMATION, *PHID_COLLECTION_INFORMATION, HID_COLLECTION_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hidclass.h
req.include-header: Hidclass.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HID_COLLECTION_INFORMATION
req.alt-loc: hidclass.h
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

# _HID_COLLECTION_INFORMATION structure



## -description
The HID_COLLECTION_INFORMATION structure contains general information about a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a>.



## -syntax

````
typedef struct _HID_COLLECTION_INFORMATION {
  ULONG   DescriptorSize;
  BOOLEAN Polled;
  UCHAR   Reserved1[1];
  USHORT  VendorID;
  USHORT  ProductID;
  USHORT  VersionNumber;
} HID_COLLECTION_INFORMATION, *PHID_COLLECTION_INFORMATION;
````


## -struct-fields

### -field DescriptorSize

Specifies the size, in bytes, of a collection's <a href="https://msdn.microsoft.com/50ac2877-4c45-4d55-b5cc-013486892fbf">preparsed data</a>.


### -field Polled

Indicates, if <b>TRUE</b>, that the HID class driver must poll the device to receive data. Otherwise, if <b>Polled</b> is <b>FALSE</b>, the device uses asynchronous interrupts to signal the host that the device has HID reports to send to the host.


### -field Reserved1

Reserved for internal system use.


### -field VendorID

Specifies a HID device's vendor ID.


### -field ProductID

Specifies a HID device's product ID.


### -field VersionNumber

Specifies the manufacturer's revision number for a HID device.


## -remarks
Kernel-mode drivers can use an <a href="..\hidclass\ni-hidclass-ioctl_hid_get_collection_information.md">IOCTL_HID_GET_COLLECTION_INFORMATION</a> to obtain a collection's <b>HID_COLLECTION_INFORMATION</b> structure.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Hidclass.h (include Hidclass.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\hidclass\ni-hidclass-ioctl_hid_get_collection_descriptor.md">IOCTL_HID_GET_COLLECTION_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\hidclass\ni-hidclass-ioctl_hid_get_collection_information.md">IOCTL_HID_GET_COLLECTION_INFORMATION</a>
</dt>
<dt>
<a href="hid.hid_collection_information">HID_COLLECTION_INFORMATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HID_COLLECTION_INFORMATION structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


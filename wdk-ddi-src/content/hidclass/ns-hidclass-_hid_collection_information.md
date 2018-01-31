---
UID : NS:hidclass._HID_COLLECTION_INFORMATION
title : "_HID_COLLECTION_INFORMATION"
author : windows-driver-content
description : The HID_COLLECTION_INFORMATION structure contains general information about a top-level collection.
old-location : hid\hid_collection_information.htm
old-project : hid
ms.assetid : 47490858-3fe0-4a94-adae-6589cad6a842
ms.author : windowsdriverdev
ms.date : 12/21/2017
ms.keywords : "*PHID_COLLECTION_INFORMATION, hidclass/PHID_COLLECTION_INFORMATION, hid.hid_collection_information, HID_COLLECTION_INFORMATION, hidstrct_d61a583e-66c7-4851-ba75-3e5973a95c70.xml, hidclass/HID_COLLECTION_INFORMATION, HID_COLLECTION_INFORMATION structure [Human Input Devices], PHID_COLLECTION_INFORMATION structure pointer [Human Input Devices], _HID_COLLECTION_INFORMATION, PHID_COLLECTION_INFORMATION"
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : hidclass.h
req.include-header : Hidclass.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PHID_COLLECTION_INFORMATION, HID_COLLECTION_INFORMATION"
---

# _HID_COLLECTION_INFORMATION structure
The HID_COLLECTION_INFORMATION structure contains general information about a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a>.

## Syntax
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

## Members


`DescriptorSize`

Specifies the size, in bytes, of a collection's <a href="https://msdn.microsoft.com/50ac2877-4c45-4d55-b5cc-013486892fbf">preparsed data</a>.

`Polled`

Indicates, if <b>TRUE</b>, that the HID class driver must poll the device to receive data. Otherwise, if <b>Polled</b> is <b>FALSE</b>, the device uses asynchronous interrupts to signal the host that the device has HID reports to send to the host.

`ProductID`

Specifies a HID device's product ID.

`Reserved1`

Reserved for internal system use.

`VendorID`

Specifies a HID device's vendor ID.

`VersionNumber`

Specifies the manufacturer's revision number for a HID device.

## Remarks
Kernel-mode drivers can use an <a href="..\hidclass\ni-hidclass-ioctl_hid_get_collection_information.md">IOCTL_HID_GET_COLLECTION_INFORMATION</a> to obtain a collection's <b>HID_COLLECTION_INFORMATION</b> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | hidclass.h (include Hidclass.h) |

## See Also

<a href="..\hidclass\ns-hidclass-_hid_collection_information.md">HID_COLLECTION_INFORMATION</a>

<a href="..\hidclass\ni-hidclass-ioctl_hid_get_collection_information.md">IOCTL_HID_GET_COLLECTION_INFORMATION</a>

<a href="..\hidclass\ni-hidclass-ioctl_hid_get_collection_descriptor.md">IOCTL_HID_GET_COLLECTION_DESCRIPTOR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HID_COLLECTION_INFORMATION structure%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
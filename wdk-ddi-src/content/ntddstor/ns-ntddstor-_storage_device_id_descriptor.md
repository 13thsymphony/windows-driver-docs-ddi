---
UID: NS.NTDDSTOR._STORAGE_DEVICE_ID_DESCRIPTOR
title: _STORAGE_DEVICE_ID_DESCRIPTOR
author: windows-driver-content
description: The STORAGE_DEVICE_ID_DESCRIPTOR structure is used in conjunction with the IOCTL_STORAGE_QUERY_PROPERTY request to retrieve the device ID descriptor data for a device.
old-location: storage\storage_device_id_descriptor.htm
old-project: storage
ms.assetid: e0e1bd3e-ee8d-40f2-904d-d6dcc4185406
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _STORAGE_DEVICE_ID_DESCRIPTOR, *PSTORAGE_DEVICE_ID_DESCRIPTOR, STORAGE_DEVICE_ID_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STORAGE_DEVICE_ID_DESCRIPTOR
req.alt-loc: ntddstor.h
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

# _STORAGE_DEVICE_ID_DESCRIPTOR structure



## -description
The <b>STORAGE_DEVICE_ID_DESCRIPTOR</b> structure is used in conjunction with the <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> request to retrieve the device ID descriptor data for a device.  



## -syntax

````
typedef struct _STORAGE_DEVICE_ID_DESCRIPTOR {
  ULONG Version;
  ULONG Size;
  ULONG NumberOfIdentifiers;
  UCHAR Identifiers[1];
} STORAGE_DEVICE_ID_DESCRIPTOR, *PSTORAGE_DEVICE_ID_DESCRIPTOR;
````


## -struct-fields

### -field Version

Indicates the version of the descriptor.


### -field Size

Indicates the size in bytes of the descriptor.


### -field NumberOfIdentifiers

Contains the number of identifiers reported by the device in the <b>Identifiers</b> array.


### -field Identifiers

Contains a variable-length array of identification descriptors.


## -remarks
The device descriptor consists of an array of device IDs taken from the SCSI-3 vital product page data that was retrieved during discovery.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddstor.h (include Ntddstor.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a>
</dt>
<dt>
<a href="storage.storage_descriptor_header">STORAGE_DESCRIPTOR_HEADER</a>
</dt>
<dt>
<a href="storage.storage_device_descriptor">STORAGE_DEVICE_DESCRIPTOR</a>
</dt>
<dt>
<a href="storage.storage_adapter_descriptor">STORAGE_ADAPTER_DESCRIPTOR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STORAGE_DEVICE_ID_DESCRIPTOR structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


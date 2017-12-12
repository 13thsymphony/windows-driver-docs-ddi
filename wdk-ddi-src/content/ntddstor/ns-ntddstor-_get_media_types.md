---
UID: NS.NTDDSTOR._GET_MEDIA_TYPES
title: _GET_MEDIA_TYPES
author: windows-driver-content
description: The GET_MEDIA_TYPES structure is used in conjunction with the IOCTL_STORAGE_GET_MEDIA_TYPES_EX request to retrieve information about the types of media supported by a device.
old-location: storage\get_media_types.htm
old-project: storage
ms.assetid: e803505f-37a0-4b20-bd6f-ce0f79eead03
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _GET_MEDIA_TYPES, *PGET_MEDIA_TYPES, GET_MEDIA_TYPES
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
req.alt-api: GET_MEDIA_TYPES
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

# _GET_MEDIA_TYPES structure



## -description
The GET_MEDIA_TYPES structure is used in conjunction with the <a href="..\ntddstor\ni-ntddstor-ioctl_storage_get_media_types_ex.md">IOCTL_STORAGE_GET_MEDIA_TYPES_EX</a> request to retrieve information about the types of media supported by a device. 



## -syntax

````
typedef struct _GET_MEDIA_TYPES {
  ULONG             DeviceType;
  ULONG             MediaInfoCount;
  DEVICE_MEDIA_INFO MediaInfo[1];
} GET_MEDIA_TYPES, *PGET_MEDIA_TYPES;
````


## -struct-fields

### -field DeviceType

Specifies one of the system-defined FILE_DEVICE_<i>XXX</i> constants indicating the type of device (such as FILE_DEVICE_DISK, FILE_DEVICE_KEYBOARD, and so forth) or a vendor-defined value for a new type of device. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563821">Specifying Device Types</a>. 


### -field MediaInfoCount

Contains the number of <a href="storage.device_media_info">DEVICE_MEDIA_INFO</a> structures in the array starting at <b>MediaInfo</b>.


### -field MediaInfo

Contains an array whose first element holds the first DEVICE_MEDIA_INFO structure in the array.


## -remarks
A storage class driver must handle the <a href="..\ntddstor\ni-ntddstor-ioctl_storage_get_media_types_ex.md">IOCTL_STORAGE_GET_MEDIA_TYPES_EX</a> request to support any device that the Removable Storage Manager (RSM) accesses, whether the device is a stand-alone device or a data transfer element (drive) in a media library or changer. 


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
<a href="..\ntddstor\ni-ntddstor-ioctl_storage_get_media_types_ex.md">IOCTL_STORAGE_GET_MEDIA_TYPES_EX</a>
</dt>
<dt>
<a href="storage.device_media_info">DEVICE_MEDIA_INFO</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20GET_MEDIA_TYPES structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


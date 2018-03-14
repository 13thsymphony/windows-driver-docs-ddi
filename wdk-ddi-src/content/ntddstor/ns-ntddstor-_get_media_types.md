---
UID: NS:ntddstor._GET_MEDIA_TYPES
title: "_GET_MEDIA_TYPES"
author: windows-driver-content
description: The GET_MEDIA_TYPES structure is used in conjunction with the IOCTL_STORAGE_GET_MEDIA_TYPES_EX request to retrieve information about the types of media supported by a device.
old-location: storage\get_media_types.htm
old-project: storage
ms.assetid: e803505f-37a0-4b20-bd6f-ce0f79eead03
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PGET_MEDIA_TYPES, GET_MEDIA_TYPES, GET_MEDIA_TYPES structure [Storage Devices], PGET_MEDIA_TYPES, PGET_MEDIA_TYPES structure pointer [Storage Devices], _GET_MEDIA_TYPES, ntddstor/GET_MEDIA_TYPES, ntddstor/PGET_MEDIA_TYPES, storage.get_media_types, structs-general_68f75a58-b2a5-4d6a-b9ba-0019e36034ef.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h, Minitape.h
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
-	ntddstor.h
api_name:
-	GET_MEDIA_TYPES
product: Windows
targetos: Windows
req.typenames: GET_MEDIA_TYPES, *PGET_MEDIA_TYPES
---

# _GET_MEDIA_TYPES structure
The GET_MEDIA_TYPES structure is used in conjunction with the <a href="..\ntddstor\ni-ntddstor-ioctl_storage_get_media_types_ex.md">IOCTL_STORAGE_GET_MEDIA_TYPES_EX</a> request to retrieve information about the types of media supported by a device.

## Syntax
````
typedef struct _GET_MEDIA_TYPES {
  ULONG             DeviceType;
  ULONG             MediaInfoCount;
  DEVICE_MEDIA_INFO MediaInfo[1];
} GET_MEDIA_TYPES, *PGET_MEDIA_TYPES;
````

## Members


`DeviceType`

Specifies one of the system-defined FILE_DEVICE_<i>XXX</i> constants indicating the type of device (such as FILE_DEVICE_DISK, FILE_DEVICE_KEYBOARD, and so forth) or a vendor-defined value for a new type of device. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563821">Specifying Device Types</a>.

`MediaInfo`

Contains an array whose first element holds the first DEVICE_MEDIA_INFO structure in the array.

`MediaInfoCount`

Contains the number of <a href="..\ntddstor\ns-ntddstor-_device_media_info.md">DEVICE_MEDIA_INFO</a> structures in the array starting at <b>MediaInfo</b>.

## Remarks
A storage class driver must handle the <a href="..\ntddstor\ni-ntddstor-ioctl_storage_get_media_types_ex.md">IOCTL_STORAGE_GET_MEDIA_TYPES_EX</a> request to support any device that the Removable Storage Manager (RSM) accesses, whether the device is a stand-alone device or a data transfer element (drive) in a media library or changer.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddstor.h (include Ntddstor.h, Minitape.h) |

## See Also

<a href="..\ntddstor\ns-ntddstor-_device_media_info.md">DEVICE_MEDIA_INFO</a>



<a href="..\ntddstor\ni-ntddstor-ioctl_storage_get_media_types_ex.md">IOCTL_STORAGE_GET_MEDIA_TYPES_EX</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20GET_MEDIA_TYPES structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
---
UID : NS:mountmgr._MOUNTDEV_NAME
title : _MOUNTDEV_NAME
author : windows-driver-content
description : The MOUNTDEV_NAME structure holds the name of a device.
old-location : storage\mountdev_name.htm
old-project : storage
ms.assetid : 26f5e98d-0709-403a-abcf-776c117d4f38
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : mountmgr/PMOUNTDEV_NAME, *PMOUNTDEV_NAME, structs-mntmgr_b7eec4f5-e4fc-4931-82e5-c6ac5cd4b48f.xml, _MOUNTDEV_NAME, storage.mountdev_name, PMOUNTDEV_NAME structure pointer [Storage Devices], mountmgr/MOUNTDEV_NAME, MOUNTDEV_NAME, PMOUNTDEV_NAME, MOUNTDEV_NAME structure [Storage Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : mountmgr.h
req.include-header : Mountmgr.h
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
req.typenames : "*PMOUNTDEV_NAME, MOUNTDEV_NAME"
---

# _MOUNTDEV_NAME structure
The MOUNTDEV_NAME structure holds the name of a device.

## Syntax
````
typedef struct _MOUNTDEV_NAME {
  USHORT NameLength;
  WCHAR  Name[1];
} MOUNTDEV_NAME, *PMOUNTDEV_NAME;
````

## Members


`Name`

Contains a variable-sized array of wide characters that holds the name of the device mount point. The name may be a nonpersistent target name such as "\Device\HarddiskVolume1", a persistent symbolic link name such as a drive letter, "\DosDevices\D:", or a mount point such as "\DosDevices\E:\FilesysD\mnt".

`NameLength`

Contains the length of the name, in bytes.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | mountmgr.h (include Mountmgr.h) |

## See Also

<a href="..\mountdev\ni-mountdev-ioctl_mountdev_link_deleted.md">IOCTL_MOUNTDEV_LINK_DELETED</a>

<a href="..\mountdev\ni-mountdev-ioctl_mountdev_link_created.md">IOCTL_MOUNTDEV_LINK_CREATED</a>

<a href="..\mountmgr\ni-mountmgr-ioctl_mountdev_query_device_name.md">IOCTL_MOUNTDEV_QUERY_DEVICE_NAME</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MOUNTDEV_NAME structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
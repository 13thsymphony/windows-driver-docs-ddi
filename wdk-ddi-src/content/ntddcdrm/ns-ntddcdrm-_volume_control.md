---
UID: NS:ntddcdrm._VOLUME_CONTROL
title: "_VOLUME_CONTROL"
author: windows-driver-content
description: The VOLUME_CONTROL structure is used in conjunction with the IOCTL_CDROM_GET_VOLUME request to retrieve volume values for up to four audio ports.
old-location: storage\volume_control.htm
old-project: storage
ms.assetid: 47512360-60fe-43f2-8052-58ca78e36d86
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PVOLUME_CONTROL, PVOLUME_CONTROL, PVOLUME_CONTROL structure pointer [Storage Devices], VOLUME_CONTROL, VOLUME_CONTROL structure [Storage Devices], _VOLUME_CONTROL, ntddcdrm/PVOLUME_CONTROL, ntddcdrm/VOLUME_CONTROL, storage.volume_control, structs-CD-ROM_d0d59b00-4eb3-4e98-b164-cb8f3e11de31.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
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
-	ntddcdrm.h
api_name:
-	VOLUME_CONTROL
product: Windows
targetos: Windows
req.typenames: VOLUME_CONTROL, *PVOLUME_CONTROL
---

# _VOLUME_CONTROL structure
The VOLUME_CONTROL structure is used in conjunction with the <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_get_volume.md">IOCTL_CDROM_GET_VOLUME</a> request to retrieve volume values for up to four audio ports.

## Syntax
````
typedef struct _VOLUME_CONTROL {
  UCHAR PortVolume[4];
} VOLUME_CONTROL, *PVOLUME_CONTROL;
````

## Members


`PortVolume`

Pointer to an array of volume values, one for each of the ports, with a maximum of four ports.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddcdrm.h (include Ntddcdrm.h) |

## See Also

<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_get_volume.md">IOCTL_CDROM_GET_VOLUME</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20VOLUME_CONTROL structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
---
UID: NS:ntdddisk._FORMAT_PARAMETERS
title: "_FORMAT_PARAMETERS"
author: windows-driver-content
description: The FORMAT_PARAMETERS structure is used in conjunction with the IOCTL_DISK_FORMAT_TRACKS request to format the specified set of contiguous tracks on the disk.
old-location: storage\format_parameters.htm
old-project: storage
ms.assetid: 9c92e010-35d7-40ff-8025-51e945861b9c
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ntdddisk/PFORMAT_PARAMETERS, FORMAT_PARAMETERS, PFORMAT_PARAMETERS structure pointer [Storage Devices], structs-disk_063eb997-3411-4101-9cde-4417647eb53f.xml, storage.format_parameters, *PFORMAT_PARAMETERS, ntdddisk/FORMAT_PARAMETERS, FORMAT_PARAMETERS structure [Storage Devices], _FORMAT_PARAMETERS, PFORMAT_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntdddisk.h
apiname:
-	FORMAT_PARAMETERS
product: Windows
targetos: Windows
req.typenames: FORMAT_PARAMETERS, *PFORMAT_PARAMETERS
---

# _FORMAT_PARAMETERS structure
The FORMAT_PARAMETERS structure is used in conjunction with the <a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_format_tracks.md">IOCTL_DISK_FORMAT_TRACKS</a> request to format the specified set of contiguous tracks on the disk.

## Syntax
````
typedef struct _FORMAT_PARAMETERS {
  MEDIA_TYPE MediaType;
  ULONG      StartCylinderNumber;
  ULONG      EndCylinderNumber;
  ULONG      StartHeadNumber;
  ULONG      EndHeadNumber;
} FORMAT_PARAMETERS, *PFORMAT_PARAMETERS;
````

## Members


`EndCylinderNumber`

Indicates the number of the cylinder where the formatting should end.

`EndHeadNumber`

Indicates the number of the head where the formatting should end.

`MediaType`

Indicates format information, such as the disk size and the number of bytes per sector. For a list of the values that can be assigned to this member, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff562216">MEDIA_TYPE</a>.

`StartCylinderNumber`

Indicates the number of the cylinder where the formatting should begin.

`StartHeadNumber`

Indicates the number of the head where the formatting should begin.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntdddisk.h (include Ntdddisk.h) |

## See Also

<a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_format_tracks.md">IOCTL_DISK_FORMAT_TRACKS</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff562216">MEDIA_TYPE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FORMAT_PARAMETERS structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
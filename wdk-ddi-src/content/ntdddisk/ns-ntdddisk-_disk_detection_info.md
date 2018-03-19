---
UID: NS:ntdddisk._DISK_DETECTION_INFO
title: "_DISK_DETECTION_INFO"
author: windows-driver-content
description: The DISK_DETECTION_INFO structure contains the detected drive parameters that are supplied by an x86 PC BIOS on boot.
old-location: storage\disk_detection_info.htm
old-project: storage
ms.assetid: 67a508cf-79c4-4c86-9ad3-fa7cca99cf5f
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PDISK_DETECTION_INFO, DISK_DETECTION_INFO, DISK_DETECTION_INFO structure [Storage Devices], PDISK_DETECTION_INFO, PDISK_DETECTION_INFO structure pointer [Storage Devices], _DISK_DETECTION_INFO, ntdddisk/DISK_DETECTION_INFO, ntdddisk/PDISK_DETECTION_INFO, storage.disk_detection_info, structs-disk_04ca1cb1-3995-47d9-9b5a-0e54ea98dbd6.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntdddisk.h
req.include-header: Ntdddisk.h, Ntddk.h, Ntdddisk.h
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
-	ntdddisk.h
api_name:
-	DISK_DETECTION_INFO
product: Windows
targetos: Windows
req.typenames: DISK_DETECTION_INFO, *PDISK_DETECTION_INFO
---

# _DISK_DETECTION_INFO structure
The DISK_DETECTION_INFO structure contains the detected drive parameters that are supplied by an x86 PC BIOS on boot.

## Syntax
````
typedef struct _DISK_DETECTION_INFO {
  ULONG          SizeOfDetectInfo;
  DETECTION_TYPE DetectionType;
  union {
    struct {
      DISK_INT13_INFO    Int13;
      DISK_EX_INT13_INFO ExInt13;
    };
  };
} DISK_DETECTION_INFO, *PDISK_DETECTION_INFO;
````

## Members


`SizeOfDetectInfo`

Contains the quantity, in bytes, of retrieved detect information.

`DetectionType`

Indicates one of three possible detection types:

<ol>
<li>
<b>DetectNone</b>

</li>
<li>
<b>DetectInt13</b>

</li>
<li>
<b>DetectExInt13</b>

</li>
</ol>
See the structure <a href="..\ntdddisk\ne-ntdddisk-_detection_type.md">DETECTION_TYPE</a> for further information.

`DUMMYUNIONNAME`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntdddisk.h (include Ntdddisk.h, Ntddk.h, Ntdddisk.h) |

## See Also

<a href="..\ntdddisk\ns-ntdddisk-_disk_geometry_ex.md">DISK_GEOMETRY_EX</a>



<a href="..\ntdddisk\ns-ntdddisk-_disk_ex_int13_info.md">DISK_EX_INT13_INFO</a>



<a href="..\ntdddisk\ns-ntdddisk-_disk_int13_info.md">DISK_INT13_INFO</a>
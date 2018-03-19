---
UID: NS:ntddcdrm._CDROM_TOC_ATIP_DATA
title: "_CDROM_TOC_ATIP_DATA"
author: windows-driver-content
description: Device control IRPs with a control code of IOCTL_CDROM_READ_TOC_EX and a format of CDROM_READ_TOC_EX_FORMAT_ATIP return their output data in this header structure followed by a series of descriptors of type CDROM_TOC_ATIP_DATA_BLOCK.
old-location: storage\cdrom_toc_atip_data.htm
old-project: storage
ms.assetid: 4caf59d4-262a-49e3-8b66-9cf29ed5cee5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PCDROM_TOC_ATIP_DATA, CDROM_TOC_ATIP_DATA, CDROM_TOC_ATIP_DATA structure [Storage Devices], PCDROM_TOC_ATIP_DATA, PCDROM_TOC_ATIP_DATA structure pointer [Storage Devices], _CDROM_TOC_ATIP_DATA, ntddcdrm/CDROM_TOC_ATIP_DATA, ntddcdrm/PCDROM_TOC_ATIP_DATA, storage.cdrom_toc_atip_data, structs-CD-ROM_57534148-0c2f-4182-8b0e-3fe4ed10505e.xml"
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
-	CDROM_TOC_ATIP_DATA
product: Windows
targetos: Windows
req.typenames: CDROM_TOC_ATIP_DATA, *PCDROM_TOC_ATIP_DATA
---

# _CDROM_TOC_ATIP_DATA structure
Device control IRPs with a control code of <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_read_toc_ex.md">IOCTL_CDROM_READ_TOC_EX</a> and a format of CDROM_READ_TOC_EX_FORMAT_ATIP return their output data in this header structure followed by a series of descriptors of type <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_toc_atip_data_block.md">CDROM_TOC_ATIP_DATA_BLOCK</a>.

## Syntax
````
typedef struct _CDROM_TOC_ATIP_DATA {
  UCHAR                     Length[2];
  UCHAR                     Reserved1;
  UCHAR                     Reserved2;
  CDROM_TOC_ATIP_DATA_BLOCK Descriptors[];
} CDROM_TOC_ATIP_DATA, *PCDROM_TOC_ATIP_DATA;
````

## Members


`Length`

Indicates the number of bytes to be transferred in response to the command. This length value does not include the length of the <b>Length </b>member itself.

`Reserved1`

Reserved.

`Reserved2`

Reserved.

`Descriptors`

Contains zero or more ATIP data block descriptors of type <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_toc_atip_data_block.md">CDROM_TOC_ATIP_DATA_BLOCK</a>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddcdrm.h (include Ntddcdrm.h) |

## See Also

<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_toc_atip_data_block.md">CDROM_TOC_ATIP_DATA_BLOCK</a>



<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_read_toc_ex.md">IOCTL_CDROM_READ_TOC_EX</a>



<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_read_toc_ex.md">CDROM_READ_TOC_EX</a>
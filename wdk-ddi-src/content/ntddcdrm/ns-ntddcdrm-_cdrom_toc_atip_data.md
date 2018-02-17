---
UID: NS:ntddcdrm._CDROM_TOC_ATIP_DATA
title: "_CDROM_TOC_ATIP_DATA"
author: windows-driver-content
description: Device control IRPs with a control code of IOCTL_CDROM_READ_TOC_EX and a format of CDROM_READ_TOC_EX_FORMAT_ATIP return their output data in this header structure followed by a series of descriptors of type CDROM_TOC_ATIP_DATA_BLOCK.
old-location: storage\cdrom_toc_atip_data.htm
old-project: storage
ms.assetid: 4caf59d4-262a-49e3-8b66-9cf29ed5cee5
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: structs-CD-ROM_57534148-0c2f-4182-8b0e-3fe4ed10505e.xml, _CDROM_TOC_ATIP_DATA, PCDROM_TOC_ATIP_DATA structure pointer [Storage Devices], PCDROM_TOC_ATIP_DATA, CDROM_TOC_ATIP_DATA structure [Storage Devices], ntddcdrm/PCDROM_TOC_ATIP_DATA, CDROM_TOC_ATIP_DATA, *PCDROM_TOC_ATIP_DATA, storage.cdrom_toc_atip_data, ntddcdrm/CDROM_TOC_ATIP_DATA
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddcdrm.h
apiname:
-	CDROM_TOC_ATIP_DATA
product: Windows
targetos: Windows
req.typenames: "*PCDROM_TOC_ATIP_DATA, CDROM_TOC_ATIP_DATA"
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


`Descriptors`

Contains zero or more ATIP data block descriptors of type <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_toc_atip_data_block.md">CDROM_TOC_ATIP_DATA_BLOCK</a>.

`Length`

Indicates the number of bytes to be transferred in response to the command. This length value does not include the length of the <b>Length </b>member itself.

`Reserved1`

Reserved.

`Reserved2`

Reserved.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddcdrm.h (include Ntddcdrm.h) |

## See Also

<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_toc_atip_data_block.md">CDROM_TOC_ATIP_DATA_BLOCK</a>



<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_read_toc_ex.md">CDROM_READ_TOC_EX</a>



<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_read_toc_ex.md">IOCTL_CDROM_READ_TOC_EX</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CDROM_TOC_ATIP_DATA structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
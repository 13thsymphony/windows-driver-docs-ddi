---
UID: NS:wdm._CLS_IO_STATISTICS_HEADER
title: "_CLS_IO_STATISTICS_HEADER"
author: windows-driver-content
description: The CLFS_IO_STATISTICS_HEADER structure holds the header portion of a CLFS_IO_STATISTICS structure.
old-location: kernel\clfs_io_statistics_header.htm
old-project: kernel
ms.assetid: ac0da755-ea2f-4b68-947c-c314d114f273
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PPCLFS_IO_STATISTICS_HEADER, kstruct_a_4b54b209-c331-4bbd-b217-d77594bd6e46.xml, _CLS_IO_STATISTICS_HEADER, PPCLS_IO_STATISTICS_HEADER structure pointer [Kernel-Mode Driver Architecture], PPCLFS_IO_STATISTICS_HEADER structure pointer [Kernel-Mode Driver Architecture], kernel.clfs_io_statistics_header, CLS_IO_STATISTICS_HEADER, *PCLFS_IO_STATISTICS_HEADER, wdm/PPCLFS_IO_STATISTICS_HEADER, PCLS_IO_STATISTICS_HEADER, PPCLS_IO_STATISTICS_HEADER, wdm/CLFS_IO_STATISTICS_HEADER, PCLS_IO_STATISTICS_HEADER structure pointer [Kernel-Mode Driver Architecture], wdm/PCLS_IO_STATISTICS_HEADER, CLS_IO_STATISTICS_HEADER structure [Kernel-Mode Driver Architecture], PCLFS_IO_STATISTICS_HEADER, wdm/CLS_IO_STATISTICS_HEADER, wdm/PCLFS_IO_STATISTICS_HEADER, CLFS_IO_STATISTICS_HEADER, PCLFS_IO_STATISTICS_HEADER structure pointer [Kernel-Mode Driver Architecture], wdm/PPCLS_IO_STATISTICS_HEADER, *PCLS_IO_STATISTICS_HEADER, CLFS_IO_STATISTICS_HEADER structure [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdm.h
apiname:
-	CLS_IO_STATISTICS_HEADER
product: Windows
targetos: Windows
req.typenames: "*PCLS_IO_STATISTICS_HEADER, CLS_IO_STATISTICS_HEADER, PPCLS_IO_STATISTICS_HEADER"
req.product: Windows 10 or later.
---

# _CLS_IO_STATISTICS_HEADER structure
The <b>CLFS_IO_STATISTICS_HEADER</b> structure holds the header portion of a <a href="..\wdm\ns-wdm-_cls_io_statistics.md">CLFS_IO_STATISTICS</a> structure.

## Syntax
````
typedef struct _CLS_IO_STATISTICS_HEADER {
  UCHAR              ubMajorVersion;
  UCHAR              ubMinorVersion;
  CLFS_IOSTATS_CLASS eStatsClass;
  USHORT             cbLength;
  ULONG              coffData;
} CLS_IO_STATISTICS_HEADER, *PCLS_IO_STATISTICS_HEADER, **PPCLS_IO_STATISTICS_HEADER, CLFS_IO_STATISTICS_HEADER, *PCLFS_IO_STATISTICS_HEADER, **PPCLFS_IO_STATISTICS_HEADER;
````

## Members


`cbLength`

The size, in bytes, of the <b>CLFS_IO_STATISTICS</b> structure, including the header.

`coffData`

The offset, in bytes, from the beginning of the <b>CLFS_IO_STATISTICS</b> structure to the beginning of the statistics data. This member allows for transparent modifications to the header.

`eStatsClass`

Reserved for future use. This member is ignored.

`ubMajorVersion`

The major version of the <a href="..\wdm\ns-wdm-_cls_io_statistics.md">CLFS_IO_STATISTICS</a> structure.

`ubMinorVersion`

The minor version of the <b>CLFS_IO_STATISTICS</b> structure.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="..\wdm\nf-wdm-clfsgetiostatistics.md">ClfsGetIoStatistics</a>



<a href="..\wdm\ns-wdm-_cls_io_statistics.md">CLFS_IO_STATISTICS</a>



<a href="..\wdm\nf-wdm-clfsgetiostatistics.md">ClfsGetIoStatistics</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20CLS_IO_STATISTICS_HEADER structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
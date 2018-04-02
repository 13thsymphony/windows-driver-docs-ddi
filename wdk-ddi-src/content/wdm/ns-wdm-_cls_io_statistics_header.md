---
UID: NS:wdm._CLS_IO_STATISTICS_HEADER
title: "_CLS_IO_STATISTICS_HEADER"
author: windows-driver-content
description: The CLFS_IO_STATISTICS_HEADER structure holds the header portion of a CLFS_IO_STATISTICS structure.
old-location: kernel\clfs_io_statistics_header.htm
old-project: kernel
ms.assetid: ac0da755-ea2f-4b68-947c-c314d114f273
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PCLFS_IO_STATISTICS_HEADER, *PCLS_IO_STATISTICS_HEADER, CLFS_IO_STATISTICS_HEADER, CLFS_IO_STATISTICS_HEADER structure [Kernel-Mode Driver Architecture], CLS_IO_STATISTICS_HEADER, CLS_IO_STATISTICS_HEADER structure [Kernel-Mode Driver Architecture], PCLFS_IO_STATISTICS_HEADER, PCLFS_IO_STATISTICS_HEADER structure pointer [Kernel-Mode Driver Architecture], PCLS_IO_STATISTICS_HEADER, PCLS_IO_STATISTICS_HEADER structure pointer [Kernel-Mode Driver Architecture], PPCLFS_IO_STATISTICS_HEADER, PPCLFS_IO_STATISTICS_HEADER structure pointer [Kernel-Mode Driver Architecture], PPCLS_IO_STATISTICS_HEADER, PPCLS_IO_STATISTICS_HEADER structure pointer [Kernel-Mode Driver Architecture], _CLS_IO_STATISTICS_HEADER, kernel.clfs_io_statistics_header, kstruct_a_4b54b209-c331-4bbd-b217-d77594bd6e46.xml, wdm/CLFS_IO_STATISTICS_HEADER, wdm/CLS_IO_STATISTICS_HEADER, wdm/PCLFS_IO_STATISTICS_HEADER, wdm/PCLS_IO_STATISTICS_HEADER, wdm/PPCLFS_IO_STATISTICS_HEADER, wdm/PPCLS_IO_STATISTICS_HEADER"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	CLS_IO_STATISTICS_HEADER
product:
- Windows
targetos: Windows
req.typenames: CLS_IO_STATISTICS_HEADER, *PCLS_IO_STATISTICS_HEADER, PPCLS_IO_STATISTICS_HEADER
req.product: Windows 10 or later.
---

# _CLS_IO_STATISTICS_HEADER structure
The <b>CLFS_IO_STATISTICS_HEADER</b> structure holds the header portion of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541794">CLFS_IO_STATISTICS</a> structure.

## Syntax
```
typedef struct _CLS_IO_STATISTICS_HEADER {
  UCHAR              ubMajorVersion;
  UCHAR              ubMinorVersion;
  CLFS_IOSTATS_CLASS eStatsClass;
  USHORT             cbLength;
  ULONG              coffData;
} *PCLS_IO_STATISTICS_HEADER, CLS_IO_STATISTICS_HEADER, PPCLS_IO_STATISTICS_HEADER;
```

## Members


`ubMajorVersion`

The major version of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541794">CLFS_IO_STATISTICS</a> structure.

`ubMinorVersion`

The minor version of the <b>CLFS_IO_STATISTICS</b> structure.

`eStatsClass`

Reserved for future use. This member is ignored.

`cbLength`

The size, in bytes, of the <b>CLFS_IO_STATISTICS</b> structure, including the header.

`coffData`

The offset, in bytes, from the beginning of the <b>CLFS_IO_STATISTICS</b> structure to the beginning of the statistics data. This member allows for transparent modifications to the header.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541794">CLFS_IO_STATISTICS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541557">ClfsGetIoStatistics</a>
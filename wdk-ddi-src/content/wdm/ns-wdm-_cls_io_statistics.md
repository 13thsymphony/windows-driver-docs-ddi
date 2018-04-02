---
UID: NS:wdm._CLS_IO_STATISTICS
title: "_CLS_IO_STATISTICS"
author: windows-driver-content
description: The CLFS_IO_STATISTICS structure holds I/O statistics data for a Common Log File System (CLFS) log.
old-location: kernel\clfs_io_statistics.htm
old-project: kernel
ms.assetid: 054d1673-0c1a-4ceb-821a-d61bf28392cf
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PCLFS_IO_STATISTICS, *PCLS_IO_STATISTICS, CLFS_IO_STATISTICS, CLFS_IO_STATISTICS structure [Kernel-Mode Driver Architecture], CLS_IO_STATISTICS, CLS_IO_STATISTICS structure [Kernel-Mode Driver Architecture], PCLFS_IO_STATISTICS, PCLFS_IO_STATISTICS structure pointer [Kernel-Mode Driver Architecture], PCLS_IO_STATISTICS, PCLS_IO_STATISTICS structure pointer [Kernel-Mode Driver Architecture], PPCLFS_IO_STATISTICS, PPCLFS_IO_STATISTICS structure pointer [Kernel-Mode Driver Architecture], PPCLS_IO_STATISTICS, PPCLS_IO_STATISTICS structure pointer [Kernel-Mode Driver Architecture], _CLS_IO_STATISTICS, kernel.clfs_io_statistics, kstruct_a_2e43db78-8c4e-462f-ad85-8c799be2f2e3.xml, wdm/CLFS_IO_STATISTICS, wdm/CLS_IO_STATISTICS, wdm/PCLFS_IO_STATISTICS, wdm/PCLS_IO_STATISTICS, wdm/PPCLFS_IO_STATISTICS, wdm/PPCLS_IO_STATISTICS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntddk.h
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
-	Wdm.h
api_name:
-	CLS_IO_STATISTICS
product:
- Windows
targetos: Windows
req.typenames: CLS_IO_STATISTICS, *PCLS_IO_STATISTICS, PPCLS_IO_STATISTICS
req.product: Windows 10 or later.
---

# _CLS_IO_STATISTICS structure
The <b>CLFS_IO_STATISTICS</b> structure holds I/O statistics data for a Common Log File System (CLFS) log.

## Syntax
```
typedef struct _CLS_IO_STATISTICS {
  CLS_IO_STATISTICS_HEADER hdrIoStats;
  ULONGLONG                cFlush;
  ULONGLONG                cbFlush;
  ULONGLONG                cMetaFlush;
  ULONGLONG                cbMetaFlush;
} *PCLS_IO_STATISTICS, CLS_IO_STATISTICS, PPCLS_IO_STATISTICS;
```

## Members


`hdrIoStats`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff541798">CLFS_IO_STATISTICS_HEADER</a> structure that holds header information for the set of statistics.

`cFlush`

The number of data flushes.

`cbFlush`

The number of bytes of data flushed.

`cMetaFlush`

The number of metadata flushes.

`cbMetaFlush`

The number of bytes of metadata flushed.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntddk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541798">CLFS_IO_STATISTICS_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541557">ClfsGetIoStatistics</a>
---
UID: NS:ehstorbandmgmt._BAND_TABLE
title: "_BAND_TABLE"
author: windows-driver-content
description: The BAND_TABLE structure contains the table of bands returned from an IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS request.
old-location: storage\band_table.htm
old-project: storage
ms.assetid: 2714E346-6BDD-49EF-9820-6B82F8F29380
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PBAND_TABLE, BAND_TABLE, BAND_TABLE structure [Storage Devices], PBAND_TABLE, PBAND_TABLE structure pointer [Storage Devices], _BAND_TABLE, ehstorbandmgmt/BAND_TABLE, ehstorbandmgmt/PBAND_TABLE, storage.band_table"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ehstorbandmgmt.h
req.include-header: EhStorBandMgmt.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8
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
-	EhStorBandMgmt.h
api_name:
-	BAND_TABLE
product:
- Windows
targetos: Windows
req.typenames: BAND_TABLE, *PBAND_TABLE
---

# _BAND_TABLE structure
The <b>BAND_TABLE</b> structure contains the table of bands returned from an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451380">IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS</a> request. The bands in the band table are selected by a match condition sent as input for <b>IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS</b> in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439719">ENUMERATE_BANDS_PARAMETERS</a> structure.

## Syntax
```
typedef struct _BAND_TABLE {
  ULONG StructSize;
  ULONG BandTableOffset;
  ULONG BandTableEntryCount;
  ULONG BandTableEntrySize;
} BAND_TABLE, *PBAND_TABLE;
```

## Members


`StructSize`

The size of this structure in bytes. Set to <b>sizeof</b>(BAND_TABLE).

`BandTableOffset`

The offset, in bytes, to the start of an array of <a href="https://msdn.microsoft.com/library/windows/hardware/hh439578">BAND_TABLE_ENTRY</a> structures.

`BandTableEntryCount`

The number of <a href="https://msdn.microsoft.com/library/windows/hardware/hh439578">BAND_TABLE_ENTRY</a> returned in the array at <b>BandTableOffset</b>.

`BandTableEntrySize`

The size of each entry, in bytes, in the array at <b>BandTableOffset</b>. Instead of using the value of <b>sizeof</b>(BAND_TABLE_ENTRY), callers must use <b>BandTableEntrySize</b> when advancing to the next element in the band table array.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8 Available starting with Windows 8 |
| **Header** | ehstorbandmgmt.h (include EhStorBandMgmt.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439578">BAND_TABLE_ENTRY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439719">ENUMERATE_BANDS_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451380">IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS</a>
---
UID: NS:ehstorbandmgmt._BAND_TABLE_ENTRY
title: "_BAND_TABLE_ENTRY"
author: windows-driver-content
description: Banding information entries in BAND_TABLE are represented as BAND_TABLE_ENTRY structures. These entries contain location and security properties for a band configuration.
old-location: storage\band_table_entry.htm
old-project: storage
ms.assetid: 6956327E-5407-4771-9BB9-F59D752A5410
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PBAND_TABLE_ENTRY, BAND_TABLE_ENTRY, BAND_TABLE_ENTRY structure [Storage Devices], PBAND_TABLE_ENTRY, PBAND_TABLE_ENTRY structure pointer [Storage Devices], _BAND_TABLE_ENTRY, ehstorbandmgmt/BAND_TABLE_ENTRY, ehstorbandmgmt/PBAND_TABLE_ENTRY, storage.band_table_entry"
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
-	BAND_TABLE_ENTRY
product:
- Windows
targetos: Windows
req.typenames: BAND_TABLE_ENTRY, *PBAND_TABLE_ENTRY
---

# _BAND_TABLE_ENTRY structure
Banding information entries in <a href="https://msdn.microsoft.com/library/windows/hardware/hh439573">BAND_TABLE</a> are represented as <b>BAND_TABLE_ENTRY</b> structures. These entries contain location and security properties for a band configuration.

## Syntax
```
typedef struct _BAND_TABLE_ENTRY {
  ULONG              BandId;
  BAND_LOCATION_INFO LocationInfo;
  BAND_SECURITY_INFO SecurityInfo;
} *PBAND_TABLE_ENTRY, BAND_TABLE_ENTRY;
```

## Members


`BandId`

The band identifier for a configured band on a storage device.

`LocationInfo`

The band location information.

`SecurityInfo`

The band security information. This includes encryption algorithm information when selected in <a href="https://msdn.microsoft.com/library/windows/hardware/hh439719">ENUMERATE_BANDS_PARAMETERS</a>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8 Available starting with Windows 8 |
| **Header** | ehstorbandmgmt.h (include EhStorBandMgmt.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439557">BAND_LOCATION_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439568">BAND_SECURITY_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439573">BAND_TABLE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439719">ENUMERATE_BANDS_PARAMETERS</a>
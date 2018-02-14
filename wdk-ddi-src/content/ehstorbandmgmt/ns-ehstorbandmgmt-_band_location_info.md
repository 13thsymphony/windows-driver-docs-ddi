---
UID: NS:ehstorbandmgmt._BAND_LOCATION_INFO
title: "_BAND_LOCATION_INFO"
author: windows-driver-content
description: The BAND_LOCATION_INFO structure specifies the location information for a band table entry query.
old-location: storage\band_location_info.htm
old-project: storage
ms.assetid: A9E28600-45B2-4082-917F-29B3237DEC84
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: BAND_LOCATION_INFO, ehstorbandmgmt/PBAND_LOCATION_INFO, PBAND_LOCATION_INFO structure pointer [Storage Devices], PBAND_LOCATION_INFO, *PBAND_LOCATION_INFO, BAND_LOCATION_INFO structure [Storage Devices], _BAND_LOCATION_INFO, ehstorbandmgmt/BAND_LOCATION_INFO, storage.band_location_info
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	EhStorBandMgmt.h
apiname:
-	BAND_LOCATION_INFO
product: Windows
targetos: Windows
req.typenames: "*PBAND_LOCATION_INFO, BAND_LOCATION_INFO"
---

# _BAND_LOCATION_INFO structure
The <b>BAND_LOCATION_INFO</b> structure specifies the location information for a band table entry query.

## Syntax
````
typedef struct _BAND_LOCATION_INFO {
  ULONG         StructSize;
  ULONG         Reserved;
  LARGE_INTEGER BandStart;
  LARGE_INTEGER BandSize;
  BYTE          Metadata[32];
} BAND_LOCATION_INFO, *PBAND_LOCATION_INFO;
````

## Members


`BandSize`

The size in bytes of the band configured at this location. This value is set to the maximum size possible for the global band.

`BandStart`

The offset in bytes of this band location on the storage device. This value is always 0 for the global band.

`Metadata`

A metadata field used as a data area for a band management application.

`Reserved`

Reserved.

`StructSize`

The size of the structure in bytes. Set to <b>sizeof</b>(BAND_LOCATION_INFO).

## Remarks
<b>BandStart</b> and <b>BandSize</b> must be a multiple of the sector size of the underlying storage device.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8 Available starting with Windows 8 |
| **Header** | ehstorbandmgmt.h (include EhStorBandMgmt.h) |

## See Also

<a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_enumerate_bands.md">IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS</a>



<a href="..\ehstorbandmgmt\ns-ehstorbandmgmt-_band_table_entry.md">BAND_TABLE_ENTRY</a>



<a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_create_band.md">IOCTL_EHSTOR_BANDMGMT_CREATE_BAND</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20BAND_LOCATION_INFO structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
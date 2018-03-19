---
UID: NS:ntddcdvd._DVD_REGION
title: "_DVD_REGION"
author: windows-driver-content
description: The DVD_REGION structure is used in conjunction with the IOCTL_DVD_GET_REGION request to retrieve region playback control (RPC) information for a DVD device.
old-location: storage\dvd_region.htm
old-project: storage
ms.assetid: a2e31a1a-59e4-4a83-b866-944ef1693f65
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PDVD_REGION, DVD_REGION, DVD_REGION structure [Storage Devices], PDVD_REGION, PDVD_REGION structure pointer [Storage Devices], _DVD_REGION, ntddcdvd/DVD_REGION, ntddcdvd/PDVD_REGION, storage.dvd_region, structs-DVD_b1569a34-c55e-482b-b87e-30becd20e2c1.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddcdvd.h
req.include-header: Ntddcdvd.h
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
-	ntddcdvd.h
api_name:
-	DVD_REGION
product: Windows
targetos: Windows
req.typenames: DVD_REGION, *PDVD_REGION
---

# _DVD_REGION structure
The DVD_REGION structure is used in conjunction with the <a href="..\ntddcdvd\ni-ntddcdvd-ioctl_dvd_get_region.md">IOCTL_DVD_GET_REGION</a> request to retrieve region playback control (RPC) information for a DVD device.

## Syntax
````
typedef struct _DVD_REGION {
  UCHAR CopySystem;
  UCHAR RegionData;
  UCHAR SystemRegion;
  UCHAR ResetCount;
} DVD_REGION, *PDVD_REGION;
````

## Members


`CopySystem`

Indicates the copyright protection type. For more information about copyright protection types, see the <i>SCSI Multimedia Commands - 3</i> (MMC-3) specification.

`RegionData`

Indicates the region code of the currently mounted DVD media. This is an eight-bit bitmask, with one bit for each DVD region. A value of 0x00 means that no region is specified.

`SystemRegion`

Indicates the region code of the DVD player. This is an eight-bit bitmask, with one bit for each system region. A value of 0x00 means that no region is specified.

`ResetCount`

Indicates the remaining number of times the DVD device's region code can be changed by the user. This member can hold a value between 0 and 7.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddcdvd.h (include Ntddcdvd.h) |

## See Also

<a href="..\ntddcdvd\ni-ntddcdvd-ioctl_dvd_get_region.md">IOCTL_DVD_GET_REGION</a>
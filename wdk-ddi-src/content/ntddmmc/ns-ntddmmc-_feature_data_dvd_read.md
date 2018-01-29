---
UID : NS:ntddmmc._FEATURE_DATA_DVD_READ
title : _FEATURE_DATA_DVD_READ
author : windows-driver-content
description : The FEATURE_DATA_DVD_READ structure contains information about the DVD Read feature.
old-location : storage\feature_data_dvd_read.htm
old-project : storage
ms.assetid : 489d3edc-4966-481e-b5c8-6979173e9341
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : FEATURE_DATA_DVD_READ structure [Storage Devices], _FEATURE_DATA_DVD_READ, structs-CD-ROM_94af17d0-72ec-4248-9035-4050f6e3c275.xml, ntddmmc/PFEATURE_DATA_DVD_READ, PFEATURE_DATA_DVD_READ, FEATURE_DATA_DVD_READ, ntddmmc/FEATURE_DATA_DVD_READ, storage.feature_data_dvd_read, *PFEATURE_DATA_DVD_READ, PFEATURE_DATA_DVD_READ structure pointer [Storage Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntddmmc.h
req.include-header : Ntddcdrm.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PFEATURE_DATA_DVD_READ, FEATURE_DATA_DVD_READ"
---

# _FEATURE_DATA_DVD_READ structure
The FEATURE_DATA_DVD_READ structure contains information about the DVD Read feature.

## Syntax
````
typedef struct _FEATURE_DATA_DVD_READ {
  FEATURE_HEADER Header;
  UCHAR          Multi110  :1;
  UCHAR          Reserved1  :7;
  UCHAR          Reserved2;
  UCHAR          DualDashR  :1;
  UCHAR          Reserved3  :7;
  UCHAR          Reserved4;
} FEATURE_DATA_DVD_READ, *PFEATURE_DATA_DVD_READ;
````

## Members


`DualDashR`



`Header`

Contains a <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a> structure with header information for this feature descriptor.

`Multi110`



`Reserved1`



`Reserved2`



`Reserved3`



`Reserved4`



## Remarks
This structure holds data for the feature named "DVD Read" by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. Devices that support this feature can read DVD-specific information from the media.

When queried, devices supporting this feature must return the information indicated in <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>. No other feature-specific information is required.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddmmc.h (include Ntddcdrm.h) |

## See Also

<a href="..\ntddmmc\ne-ntddmmc-_feature_number.md">FEATURE_NUMBER</a>

<a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_DATA_DVD_READ structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
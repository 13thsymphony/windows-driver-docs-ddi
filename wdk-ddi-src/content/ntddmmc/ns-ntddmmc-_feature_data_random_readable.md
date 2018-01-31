---
UID : NS:ntddmmc._FEATURE_DATA_RANDOM_READABLE
title : "_FEATURE_DATA_RANDOM_READABLE"
author : windows-driver-content
description : The FEATURE_DATA_RANDOM_READABLE structure contains data for the random readable feature.
old-location : storage\feature_data_random_readable.htm
old-project : storage
ms.assetid : c235a3aa-f8fe-4034-a645-ef85b2574fa0
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : FEATURE_DATA_RANDOM_READABLE, FEATURE_DATA_RANDOM_READABLE structure [Storage Devices], ntddmmc/FEATURE_DATA_RANDOM_READABLE, PFEATURE_DATA_RANDOM_READABLE, *PFEATURE_DATA_RANDOM_READABLE, storage.feature_data_random_readable, PFEATURE_DATA_RANDOM_READABLE structure pointer [Storage Devices], _FEATURE_DATA_RANDOM_READABLE, ntddmmc/PFEATURE_DATA_RANDOM_READABLE, structs-CD-ROM_90540677-8abb-43d0-919a-821411398074.xml
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
req.typenames : "*PFEATURE_DATA_RANDOM_READABLE, FEATURE_DATA_RANDOM_READABLE"
---

# _FEATURE_DATA_RANDOM_READABLE structure
The FEATURE_DATA_RANDOM_READABLE structure contains data for the random readable feature.

## Syntax
````
typedef struct _FEATURE_DATA_RANDOM_READABLE {
  FEATURE_HEADER Header;
  UCHAR          LogicalBlockSize[4];
  UCHAR          Blocking[2];
  UCHAR          ErrorRecoveryPagePresent  :1;
  UCHAR          Reserved1  :7;
  UCHAR          Reserved2;
} FEATURE_DATA_RANDOM_READABLE, *PFEATURE_DATA_RANDOM_READABLE;
````

## Members


`Blocking`

Indicates the number of logical blocks per device-readable unit. The bytes of this value are arranged in big-endian order. <b>Blocking</b>[0] contains the most significant byte, and <b>Blocking</b>[1] contains the least significant byte.

`ErrorRecoveryPagePresent`

Indicates, when set to zero, that the read/write error recovery mode page might not be present. When set to 1, it indicates that the error recovery page is present.

`Header`

Contains a <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a> structure with header information for this feature descriptor.

`LogicalBlockSize`

Indicates the number of bytes per logical block. The bytes of this value are arranged in big-endian order. <b>LogicalBlockSize</b>[0] contains the most significant byte, and <b>LogicalBlockSize</b>[3] contains the least significant byte.

`Reserved1`

Reserved.

`Reserved2`

Reserved.

## Remarks
This structure holds data for the feature named "Random Readable" by the <i>MMC-3 </i>specification. Devices that support this feature allow the initiator to read blocks of data on the disk at random locations. These devices do not require that the initiator address disk locations in any particular order.

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

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_DATA_RANDOM_READABLE structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
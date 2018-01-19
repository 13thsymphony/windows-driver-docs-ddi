---
UID : NS:ntddmmc._FEATURE_DATA_SECTOR_ERASABLE
title : _FEATURE_DATA_SECTOR_ERASABLE
author : windows-driver-content
description : The FEATURE_DATA_SECTOR_ERASABLE structure contains information for the Sector Erasable feature.
old-location : storage\feature_data_sector_erasable.htm
old-project : storage
ms.assetid : 6f714e13-a844-4afa-9002-52a5318a7659
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _FEATURE_DATA_SECTOR_ERASABLE, FEATURE_DATA_SECTOR_ERASABLE, *PFEATURE_DATA_SECTOR_ERASABLE
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
req.alt-api : FEATURE_DATA_SECTOR_ERASABLE
req.alt-loc : ntddmmc.h
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
req.typenames : FEATURE_DATA_SECTOR_ERASABLE, *PFEATURE_DATA_SECTOR_ERASABLE
---

# _FEATURE_DATA_SECTOR_ERASABLE structure
The FEATURE_DATA_SECTOR_ERASABLE structure contains information for the Sector Erasable feature.

## Syntax
````
typedef struct _FEATURE_DATA_SECTOR_ERASABLE {
  FEATURE_HEADER Header;
} FEATURE_DATA_SECTOR_ERASABLE, *PFEATURE_DATA_SECTOR_ERASABLE;
````

## Members

        
            `Header`

            Contains a <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a> structure with header information for this feature descriptor.

    ## Remarks
        This structure holds data for the feature named "Sector Erasable" by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. Devices that support this feature can erase media. These devices also require an erase pass before overwriting existing data.

When queried, devices supporting this feature must return the information indicated in <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>. No other feature-specific information is required.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddmmc.h (include Ntddcdrm.h) |

    ## See Also

        <dl>
<dt>
<a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>
</dt>
<dt>
<a href="..\ntddmmc\ne-ntddmmc-_feature_number.md">FEATURE_NUMBER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_DATA_SECTOR_ERASABLE structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
---
UID : NS:ntddmmc._FEATURE_DATA_SMART
title : _FEATURE_DATA_SMART
author : windows-driver-content
description : The FEATURE_DATA_SMART structure holds data for the S.M.A.R.T. feature.
old-location : storage\feature_data_smart.htm
old-project : storage
ms.assetid : cf6578d1-e455-4bbe-a89f-bc0292e24a4a
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _FEATURE_DATA_SMART, FEATURE_DATA_SMART, *PFEATURE_DATA_SMART
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
req.alt-api : FEATURE_DATA_SMART
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
req.typenames : FEATURE_DATA_SMART, *PFEATURE_DATA_SMART
---

# _FEATURE_DATA_SMART structure
The FEATURE_DATA_SMART structure holds data for the S.M.A.R.T. feature.

## Syntax
````
typedef struct _FEATURE_DATA_SMART {
  FEATURE_HEADER Header;
  UCHAR          FaultFailureReportingPagePresent  :1;
  UCHAR          Reserved1  :7;
  UCHAR          Reserved02[3];
} FEATURE_DATA_SMART, *PFEATURE_DATA_SMART;
````

## Members

        
            `FaultFailureReportingPagePresent`

            Indicates, when set to 1, that the device supports the Fault / Failure Reporting Mode. If set to zero, the device does not support this mode.
        
            `Header`

            Contains a <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a> structure with header information for this feature descriptor.
        
            `Reserved02`

            Reserved.
        
            `Reserved1`

            Reserved.

    ## Remarks
        This structure holds data for the feature named "S.M.A.R.T." by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. Devices that support this feature support Self-Monitoring Analysis and Reporting Technology (SMART).

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
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_DATA_SMART structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
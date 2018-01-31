---
UID : NS:ntddmmc._FEATURE_DATA_WRITE_PROTECT
title : "_FEATURE_DATA_WRITE_PROTECT"
author : windows-driver-content
description : The FEATURE_DATA_WRITE_PROTECT structure contains information about the Write Protect feature.
old-location : storage\feature_data_write_protect.htm
old-project : storage
ms.assetid : 16582fce-179a-4a99-9e4c-6f7ca1d3ddef
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : storage.feature_data_write_protect, FEATURE_DATA_WRITE_PROTECT structure [Storage Devices], PFEATURE_DATA_WRITE_PROTECT structure pointer [Storage Devices], ntddmmc/FEATURE_DATA_WRITE_PROTECT, PFEATURE_DATA_WRITE_PROTECT, *PFEATURE_DATA_WRITE_PROTECT, ntddmmc/PFEATURE_DATA_WRITE_PROTECT, structs-CD-ROM_67c6f24f-271e-4452-8b5f-fc6719c1d291.xml, _FEATURE_DATA_WRITE_PROTECT, FEATURE_DATA_WRITE_PROTECT
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
req.typenames : "*PFEATURE_DATA_WRITE_PROTECT, FEATURE_DATA_WRITE_PROTECT"
---

# _FEATURE_DATA_WRITE_PROTECT structure
The FEATURE_DATA_WRITE_PROTECT structure contains information about the Write Protect feature.

## Syntax
````
typedef struct _FEATURE_DATA_WRITE_PROTECT {
  FEATURE_HEADER Header;
  UCHAR          SupportsSWPPBit  :1;
  UCHAR          SupportsPersistentWriteProtect  :1;
  UCHAR          WriteInhibitDCB  :1;
  UCHAR          DiscWriteProtectPAC  :1;
  UCHAR          Reserved01  :4;
  UCHAR          Reserved2[3];
} FEATURE_DATA_WRITE_PROTECT, *PFEATURE_DATA_WRITE_PROTECT;
````

## Members


`DiscWriteProtectPAC`



`Header`

Contains a <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a> structure with header information for this feature descriptor.

`Reserved01`



`Reserved2`

Reserved.

`SupportsPersistentWriteProtect`

Indicates, when set to 1, that the device supports the persistent write protect bit of the time-out &amp; protect mode page. For more details on the write protect feature see the <i>SCSI Multimedia - 4 (MMC-4)</i> specification.

`SupportsSWPPBit`

Indicates, when set to 1, that the device supports set/release PWP status. If additionally <b>SupportsPersistentWriteProtect</b> is set to 1, the device supports the SEND DVD STRUCTURE command with Format = 0xC0. For more details on the write protect feature see the <i>SCSI Multimedia - 4 (MMC-4)</i> specification.

`WriteInhibitDCB`



## Remarks
This structure holds data for the feature named "Write Protect" by the <i>MMC-3 </i>specification. Devices that support this feature allow the initiator to change the write-protection state of the media programmatically.

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

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_DATA_WRITE_PROTECT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
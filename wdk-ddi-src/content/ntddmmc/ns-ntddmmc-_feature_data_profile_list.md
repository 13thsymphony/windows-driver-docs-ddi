---
UID: NS:ntddmmc._FEATURE_DATA_PROFILE_LIST
title: "_FEATURE_DATA_PROFILE_LIST"
author: windows-driver-content
description: The FEATURE_DATA_PROFILE_LIST structure contains the data for a profile list descriptor.
old-location: storage\feature_data_profile_list.htm
old-project: storage
ms.assetid: 77b8c789-0f3d-43b5-95ff-15d93b67cbe3
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PFEATURE_DATA_PROFILE_LIST, FEATURE_DATA_PROFILE_LIST, FEATURE_DATA_PROFILE_LIST structure [Storage Devices], PFEATURE_DATA_PROFILE_LIST, PFEATURE_DATA_PROFILE_LIST structure pointer [Storage Devices], _FEATURE_DATA_PROFILE_LIST, ntddmmc/FEATURE_DATA_PROFILE_LIST, ntddmmc/PFEATURE_DATA_PROFILE_LIST, storage.feature_data_profile_list, structs-CD-ROM_fae1990f-a605-4281-a8e6-e8e08431493d.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddmmc.h
req.include-header: Ntddcdrm.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddmmc.h
api_name:
-	FEATURE_DATA_PROFILE_LIST
product: Windows
targetos: Windows
req.typenames: FEATURE_DATA_PROFILE_LIST, *PFEATURE_DATA_PROFILE_LIST
---

# _FEATURE_DATA_PROFILE_LIST structure
The FEATURE_DATA_PROFILE_LIST structure contains the data for a profile list descriptor.

## Syntax
```
typedef struct _FEATURE_DATA_PROFILE_LIST {
  FEATURE_HEADER               Header;
  FEATURE_DATA_PROFILE_LIST_EX Profiles[0];
} FEATURE_DATA_PROFILE_LIST, *PFEATURE_DATA_PROFILE_LIST;
```

## Members


`Header`

Contains a header that indicates how many profiles are reported in the profile list descriptor. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a> structure is used to describe both feature and profile list descriptors. When FEATURE_HEADER is used with a profile list descriptor the <b>FeatureCode</b> member of FEATURE_HEADER must be set to zero, the <b>Current</b> member must be set to 1, the <b>Version</b> member must be set to zero, and the <b>Persistent</b> member must be set to 1. The <b>Persistent</b> member is set to 1, because all devices that are compliant with the <i>SCSI Multimedia - 4 (MMC-4)</i> standard must support reporting of the profile list. The <b>AdditionalLength</b> member must be set to ((number of profile descriptors) * 4). See the <i>MMC-3 </i>specification For more information about the values assigned to these members.

`Profiles`

Contains a variable length array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff553818">FEATURE_DATA_PROFILE_LIST_EX</a> structures that describe all the profiles supported by the device.

## Remarks
This structure holds data for the feature named "Profile List" by the <i>MMC-3 </i>specification. This feature provides a list of all profiles supported by the device.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddmmc.h (include Ntddcdrm.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553818">FEATURE_DATA_PROFILE_LIST_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553851">FEATURE_PROFILE_TYPE</a>
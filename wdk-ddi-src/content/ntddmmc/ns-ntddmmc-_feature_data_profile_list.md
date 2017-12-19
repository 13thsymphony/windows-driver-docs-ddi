---
UID: NS.NTDDMMC._FEATURE_DATA_PROFILE_LIST
title: _FEATURE_DATA_PROFILE_LIST
author: windows-driver-content
description: The FEATURE_DATA_PROFILE_LIST structure contains the data for a profile list descriptor.
old-location: storage\feature_data_profile_list.htm
old-project: storage
ms.assetid: 77b8c789-0f3d-43b5-95ff-15d93b67cbe3
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _FEATURE_DATA_PROFILE_LIST, PFEATURE_DATA_PROFILE_LIST, *PFEATURE_DATA_PROFILE_LIST, FEATURE_DATA_PROFILE_LIST
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
req.alt-api: FEATURE_DATA_PROFILE_LIST
req.alt-loc: ntddmmc.h
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
---

# _FEATURE_DATA_PROFILE_LIST structure



## -description
The FEATURE_DATA_PROFILE_LIST structure contains the data for a profile list descriptor. 



## -syntax

````
typedef struct _FEATURE_DATA_PROFILE_LIST {
  FEATURE_HEADER               Header;
  FEATURE_DATA_PROFILE_LIST_EX Profiles[];
} FEATURE_DATA_PROFILE_LIST, *PFEATURE_DATA_PROFILE_LIST;
````


## -struct-fields

### -field Header

Contains a header that indicates how many profiles are reported in the profile list descriptor. The <a href="storage.feature_header">FEATURE_HEADER</a> structure is used to describe both feature and profile list descriptors. When FEATURE_HEADER is used with a profile list descriptor the <b>FeatureCode</b> member of FEATURE_HEADER must be set to zero, the <b>Current</b> member must be set to 1, the <b>Version</b> member must be set to zero, and the <b>Persistent</b> member must be set to 1. The <b>Persistent</b> member is set to 1, because all devices that are compliant with the <i>SCSI Multimedia - 4 (MMC-4)</i> standard must support reporting of the profile list. The <b>AdditionalLength</b> member must be set to ((number of profile descriptors) * 4). See the <i>MMC-3 </i>specification For more information about the values assigned to these members. 


### -field Profiles

Contains a variable length array of <a href="storage.feature_data_profile_list_ex">FEATURE_DATA_PROFILE_LIST_EX</a> structures that describe all the profiles supported by the device. 


## -remarks
This structure holds data for the feature named "Profile List" by the <i>MMC-3 </i>specification. This feature provides a list of all profiles supported by the device. 


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddmmc.h (include Ntddcdrm.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.feature_profile_type">FEATURE_PROFILE_TYPE</a>
</dt>
<dt>
<a href="storage.feature_data_profile_list_ex">FEATURE_DATA_PROFILE_LIST_EX</a>
</dt>
<dt>
<a href="storage.feature_header">FEATURE_HEADER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_DATA_PROFILE_LIST structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


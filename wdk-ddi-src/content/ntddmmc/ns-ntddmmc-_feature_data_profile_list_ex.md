---
UID: NS:ntddmmc._FEATURE_DATA_PROFILE_LIST_EX
title: _FEATURE_DATA_PROFILE_LIST_EX
author: windows-driver-content
description: The FEATURE_DATA_PROFILE_LIST_EX structure contains information corresponding to a profile list element in a profile list descriptor.
old-location: storage\feature_data_profile_list_ex.htm
old-project: storage
ms.assetid: c15f9be2-1f35-41cf-a1de-880e3662f2b4
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _FEATURE_DATA_PROFILE_LIST_EX, FEATURE_DATA_PROFILE_LIST_EX, *PFEATURE_DATA_PROFILE_LIST_EX
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
req.alt-api: FEATURE_DATA_PROFILE_LIST_EX
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
req.typenames: FEATURE_DATA_PROFILE_LIST_EX, *PFEATURE_DATA_PROFILE_LIST_EX
---

# _FEATURE_DATA_PROFILE_LIST_EX structure



## -description
The FEATURE_DATA_PROFILE_LIST_EX structure contains information corresponding to a profile list element in a profile list descriptor. 



## -syntax

````
typedef struct _FEATURE_DATA_PROFILE_LIST_EX {
  UCHAR ProfileNumber[2];
  UCHAR Current  :1;
  UCHAR Reserved1  :7;
  UCHAR Reserved2;
} FEATURE_DATA_PROFILE_LIST_EX, *PFEATURE_DATA_PROFILE_LIST_EX;
````


## -struct-fields

### -field ProfileNumber

Contains the profile number. This number must be one of the values defined by the <a href="..\ntddmmc\ne-ntddmmc-_feature_profile_type.md">FEATURE_PROFILE_TYPE</a> enumeration. <b>ProfileNumber</b>[0] must contain the most significant byte of the profile number. <b>ProfileNumber</b>[1] must contain the least significant byte. 


### -field Current

Indicates, when set to 1, that this feature is currently active and the feature data is valid. When set to zero, this bit indicates that the feature is not currently active and that the feature data might not be valid. 


### -field Reserved1

Reserved. 


### -field Reserved2

Reserved. 


## -remarks


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
<a href="..\ntddmmc\ne-ntddmmc-_feature_profile_type.md">FEATURE_PROFILE_TYPE</a>
</dt>
<dt>
<a href="..\ntddmmc\ns-ntddmmc-_feature_data_profile_list.md">FEATURE_DATA_PROFILE_LIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_DATA_PROFILE_LIST_EX structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


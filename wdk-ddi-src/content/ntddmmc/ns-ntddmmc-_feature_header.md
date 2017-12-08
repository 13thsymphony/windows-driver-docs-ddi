---
UID: NS.NTDDMMC._FEATURE_HEADER
title: _FEATURE_HEADER
author: windows-driver-content
description: The FEATURE_HEADER structure is used in conjunction with the IOCTL_CDROM_GET_CONFIGURATION request to report header information for both feature and profile descriptors.
old-location: storage\feature_header.htm
old-project: storage
ms.assetid: 61831fbb-48ad-4831-8b69-7b1a5cafa629
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: _FEATURE_HEADER, FEATURE_HEADER, *PFEATURE_HEADER
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
req.alt-api: FEATURE_HEADER
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

# _FEATURE_HEADER structure



## -description
The FEATURE_HEADER structure is used in conjunction with the <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_get_configuration.md">IOCTL_CDROM_GET_CONFIGURATION</a> request to report header information for both feature and profile descriptors.


## -syntax

````
typedef struct _FEATURE_HEADER {
  UCHAR FeatureCode[2];
  UCHAR Current  :1;
  UCHAR Persistent  :1;
  UCHAR Version  :4;
  UCHAR Reserved0  :2;
  UCHAR AdditionalLength;
} FEATURE_HEADER, *PFEATURE_HEADER;
````


## -struct-fields

### -field FeatureCode

Contains a value between zero and 0xffff that indicates a feature. The <a href="storage.feature_number">FEATURE_NUMBER</a> enumeration provides a list of currently supported feature numbers. <b>FeatureCode</b>[0] contains the most significant byte of the feature number. <b>FeatureCode</b>[1] contains the least significant byte. 

### -field Current

Indicates, when set to 1, that this feature is currently active and the data reported for the feature is valid. When set to zero, this bit indicates that the feature is not currently active and that the data reported for the feature might not be valid. 

### -field Persistent

Indicates, when set to 1, that the feature is always active. When set to zero, this bit indicates that the feature is not always active. 

### -field Version

Must be set to zero unless otherwise specified within the description for a particular feature.

### -field Reserved0

Reserved.

### -field AdditionalLength

Indicates the number of bytes of feature information that follow this header. This member must be an integral multiple of 4. The total size of the data related to this feature will be <b>AdditionalLength</b> + <b>sizeof</b>(FEATURE_HEADER).

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
<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_get_configuration.md">IOCTL_CDROM_GET_CONFIGURATION</a>
</dt>
<dt>
<a href="storage.get_configuration_header">GET_CONFIGURATION_HEADER</a>
</dt>
<dt>
<a href="storage.feature_number">FEATURE_NUMBER</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_HEADER structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

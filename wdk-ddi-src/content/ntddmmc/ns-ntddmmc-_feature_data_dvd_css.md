---
UID: NS.NTDDMMC._FEATURE_DATA_DVD_CSS
title: _FEATURE_DATA_DVD_CSS
author: windows-driver-content
description: The FEATURE_DATA_DVD_CSS structure holds information about the DVD Content Scrambling System (CSS) feature.
old-location: storage\feature_data_dvd_css.htm
old-project: storage
ms.assetid: 8266f17d-65d6-49a0-a8ea-fee71dff4db0
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _FEATURE_DATA_DVD_CSS, PFEATURE_DATA_DVD_CSS, *PFEATURE_DATA_DVD_CSS, FEATURE_DATA_DVD_CSS
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
req.alt-api: FEATURE_DATA_DVD_CSS
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

# _FEATURE_DATA_DVD_CSS structure



## -description
The FEATURE_DATA_DVD_CSS structure holds information about the DVD Content Scrambling System (CSS) feature.



## -syntax

````
typedef struct _FEATURE_DATA_DVD_CSS {
  FEATURE_HEADER Header;
  UCHAR          Reserved1[3];
  UCHAR          CssVersion;
} FEATURE_DATA_DVD_CSS, *PFEATURE_DATA_DVD_CSS;
````


## -struct-fields

### -field Header

Contains a <a href="storage.feature_header">FEATURE_HEADER</a> structure with header information for this feature descriptor. 


### -field Reserved1

Reserved. 


### -field CssVersion

Must be set to 1. 


## -remarks
This structure holds data for the feature named "DVD-CSS" by the <i>MMC-3 </i>specification. Devices that support this feature can perform DVD Content Scrambling System (DVD-CSS) authentication and key management. 


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
<a href="storage.feature_header">FEATURE_HEADER</a>
</dt>
<dt>
<a href="storage.feature_number">FEATURE_NUMBER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_DATA_DVD_CSS structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


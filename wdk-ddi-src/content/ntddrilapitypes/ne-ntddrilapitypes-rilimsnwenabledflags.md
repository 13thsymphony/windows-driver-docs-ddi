---
UID: NE.ntddrilapitypes.RILIMSNWENABLEDFLAGS
title: RILIMSNWENABLEDFLAGS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilimsnwenabledflags.htm
old-project: netvista
ms.assetid: ae13790a-2442-4a8e-88cb-2cb6c8e02da6
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: RILIMSNWENABLEDFLAGS, RILIMSNWENABLEDFLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILIMSNWENABLEDFLAGS
req.alt-loc: ntddrilapitypes.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
---

# RILIMSNWENABLEDFLAGS enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef enum _RILIMSNWENABLEDFLAGS { 
  RIL_IMS_NW_ENABLED_FLAG_PROVISION,
  RIL_IMS_NW_ENABLED_FLAG_VOICE,
  RIL_IMS_NW_ENABLED_FLAG_VIDEO,
  RIL_IMS_NW_ENABLED_FLAG_EAB,
  RIL_IMS_NW_ENABLED_FLAG_ALL
} RILIMSNWENABLEDFLAGS;
````


## -enum-fields

### -field RIL_IMS_NW_ENABLED_FLAG_PROVISION


### -field RIL_IMS_NW_ENABLED_FLAG_VOICE


### -field RIL_IMS_NW_ENABLED_FLAG_VIDEO


### -field RIL_IMS_NW_ENABLED_FLAG_EAB


### -field RIL_IMS_NW_ENABLED_FLAG_ALL


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddrilapitypes.h</dt>
</dl>
</td>
</tr>
</table>
---
UID: NE.ntddrilapitypes.RILCALLMEDIATYPE
title: RILCALLMEDIATYPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmediatype.htm
old-project: netvista
ms.assetid: 993013f1-5026-4c30-b4df-958606adc8fa
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RILCALLMEDIATYPE, RILCALLMEDIATYPE
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
req.alt-api: RILCALLMEDIATYPE
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

# RILCALLMEDIATYPE enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax

````
typedef enum _RILCALLMEDIATYPE { 
  RIL_CALLMEDIATYPE_AUDIO,
  RIL_CALLMEDIATYPE_VIDEO,
  RIL_CALLMEDIATYPE_CUSTOM,
  RIL_CALLMEDIATYPE_MAX
} RILCALLMEDIATYPE;
````


## -enum-fields

### -field RIL_CALLMEDIATYPE_AUDIO


### -field RIL_CALLMEDIATYPE_VIDEO


### -field RIL_CALLMEDIATYPE_CUSTOM


### -field RIL_CALLMEDIATYPE_MAX


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
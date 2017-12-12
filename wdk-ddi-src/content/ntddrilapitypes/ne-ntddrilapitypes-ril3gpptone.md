---
UID: NE.ntddrilapitypes.RIL3GPPTONE
title: RIL3GPPTONE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril3gpptone.htm
old-project: netvista
ms.assetid: 3dd7c317-b77f-4cc1-8513-ed305418e76f
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: RIL3GPPTONE, RIL3GPPTONE
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
req.alt-api: RIL3GPPTONE
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

# RIL3GPPTONE enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef enum _RIL3GPPTONE { 
  RIL_3GPPTONE_RINGBACK,
  RIL_3GPPTONE_BUSY,
  RIL_3GPPTONE_CONGESTION,
  RIL_3GPPTONE_AUTHENTICATIONFAILURE,
  RIL_3GPPTONE_NUMBERUNOBTAINABLE,
  RIL_3GPPTONE_CALLDROPPED,
  RIL_3GPPTONE_MAX
} RIL3GPPTONE;
````


## -enum-fields

### -field RIL_3GPPTONE_RINGBACK


### -field RIL_3GPPTONE_BUSY


### -field RIL_3GPPTONE_CONGESTION


### -field RIL_3GPPTONE_AUTHENTICATIONFAILURE


### -field RIL_3GPPTONE_NUMBERUNOBTAINABLE


### -field RIL_3GPPTONE_CALLDROPPED


### -field RIL_3GPPTONE_MAX


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
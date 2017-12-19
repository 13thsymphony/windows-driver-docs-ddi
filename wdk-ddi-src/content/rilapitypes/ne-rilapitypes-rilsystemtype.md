---
UID: NE.rilapitypes.RILSYSTEMTYPE
title: RILSYSTEMTYPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsystemtype_2.htm
old-project: NetVista
ms.assetid: 5342333e-6119-4800-896e-4c388706d97e
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RILSYSTEMTYPE, RILSYSTEMTYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILSYSTEMTYPE
req.alt-loc: rilapitypes.h
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
req.product: Windows 10 or later.
---

# RILSYSTEMTYPE enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef enum _RILSYSTEMTYPE { 
  RIL_SYSTEMTYPE_1XRTT,
  RIL_SYSTEMTYPE_EVDO,
  RIL_SYSTEMTYPE_GSM,
  RIL_SYSTEMTYPE_UMTS,
  RIL_SYSTEMTYPE_LTE,
  RIL_SYSTEMTYPE_TDSCDMA,
  RIL_SYSTEMTYPE_CDMA,
  RIL_SYSTEMTYPE_GSMUMTS,
  RIL_SYSTEMTYPE_GSMTDS,
  RIL_SYSTEMTYPE_GSMUMTSTDS,
  RIL_SYSTEMTYPE_3GPP,
  RIL_SYSTEMTYPE_ALL
} RILSYSTEMTYPE;
````


## -enum-fields

### -field RIL_SYSTEMTYPE_1XRTT


### -field RIL_SYSTEMTYPE_EVDO


### -field RIL_SYSTEMTYPE_GSM


### -field RIL_SYSTEMTYPE_UMTS


### -field RIL_SYSTEMTYPE_LTE


### -field RIL_SYSTEMTYPE_TDSCDMA


### -field RIL_SYSTEMTYPE_CDMA


### -field RIL_SYSTEMTYPE_GSMUMTS


### -field RIL_SYSTEMTYPE_GSMTDS


### -field RIL_SYSTEMTYPE_GSMUMTSTDS


### -field RIL_SYSTEMTYPE_3GPP


### -field RIL_SYSTEMTYPE_ALL


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Rilapitypes.h</dt>
</dl>
</td>
</tr>
</table>
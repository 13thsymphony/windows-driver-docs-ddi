---
UID: NE.rilapitypes.RILDIALPARAMSOPTIONS
title: RILDIALPARAMSOPTIONS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rildialparamsoptions_2.htm
old-project: NetVista
ms.assetid: c2635f91-005f-45e7-9d6c-92caca7f4452
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RILDIALPARAMSOPTIONS, RILDIALPARAMSOPTIONS
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
req.alt-api: RILDIALPARAMSOPTIONS
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

# RILDIALPARAMSOPTIONS enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef enum _RILDIALPARAMSOPTIONS { 
  RIL_DIALOPT_RESTRICTID,
  RIL_DIALOPT_PRESENTID,
  RIL_DIALOPT_ANYEXECUTORFOREMERGENCY,
  RIL_DIALOPT_RTTFULL,
  RIL_DIALOPT_ALL
} RILDIALPARAMSOPTIONS;
````


## -enum-fields

### -field RIL_DIALOPT_RESTRICTID


### -field RIL_DIALOPT_PRESENTID


### -field RIL_DIALOPT_ANYEXECUTORFOREMERGENCY


### -field RIL_DIALOPT_RTTFULL


### -field RIL_DIALOPT_ALL


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
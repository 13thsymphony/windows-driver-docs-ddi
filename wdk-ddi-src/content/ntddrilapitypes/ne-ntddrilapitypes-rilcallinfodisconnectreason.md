---
UID: NE.ntddrilapitypes.RILCALLINFODISCONNECTREASON
title: RILCALLINFODISCONNECTREASON
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallinfodisconnectreason.htm
old-project: NetVista
ms.assetid: 2e339b56-9130-4459-8ccd-171f721ae83e
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RILCALLINFODISCONNECTREASON, RILCALLINFODISCONNECTREASON
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
req.alt-api: RILCALLINFODISCONNECTREASON
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

# RILCALLINFODISCONNECTREASON enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef enum _RILCALLINFODISCONNECTREASON { 
  RIL_DISCREASON_BUSY,
  RIL_DISCREASON_NETWORKERROR,
  RIL_DISCREASON_RADIOFADE,
  RIL_DISCREASON_CONGESTION,
  RIL_DISCREASON_EMERGENCYONLY,
  RIL_DISCREASON_NOSERVICE,
  RIL_DISCREASON_OTHEREXECUTORBUSY,
  RIL_DISCREASON_EMERGENCYFAILOVER,
  RIL_DISCREASON_HANDOVER_MERGE,
  RIL_DISCREASON_MAX
} RILCALLINFODISCONNECTREASON;
````


## -enum-fields

### -field RIL_DISCREASON_BUSY


### -field RIL_DISCREASON_NETWORKERROR


### -field RIL_DISCREASON_RADIOFADE


### -field RIL_DISCREASON_CONGESTION


### -field RIL_DISCREASON_EMERGENCYONLY


### -field RIL_DISCREASON_NOSERVICE


### -field RIL_DISCREASON_OTHEREXECUTORBUSY


### -field RIL_DISCREASON_EMERGENCYFAILOVER


### -field RIL_DISCREASON_HANDOVER_MERGE


### -field RIL_DISCREASON_MAX


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
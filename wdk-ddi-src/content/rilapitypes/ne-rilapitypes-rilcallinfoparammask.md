---
UID: NE.rilapitypes.RILCALLINFOPARAMMASK
title: RILCALLINFOPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallinfoparammask_2.htm
old-project: netvista
ms.assetid: 8e5935d9-382f-409d-a9ed-9381613b5d9c
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: RILCALLINFOPARAMMASK, RILCALLINFOPARAMMASK
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
req.alt-api: RILCALLINFOPARAMMASK
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

# RILCALLINFOPARAMMASK enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef enum _RILCALLINFOPARAMMASK { 
  RIL_PARAM_CI_ID,
  RIL_PARAM_CI_DIRECTION,
  RIL_PARAM_CI_STATUS,
  RIL_PARAM_CI_TYPE,
  RIL_PARAM_CI_MULTIPARTY,
  RIL_PARAM_CI_ADDRESS,
  RIL_PARAM_CI_SUBADDRESS,
  RIL_PARAM_CI_DESCRIPTION,
  RIL_PARAM_CI_NUM_PRES_IND,
  RIL_PARAM_CI_NAME_PRES_IND,
  RIL_PARAM_CI_FLAGS,
  RIL_PARAM_CI_DISCONNECTINITIATOR,
  RIL_PARAM_CI_DISCONNECTREASON,
  RIL_PARAM_CI_DISCONNECTDETAILS,
  RIL_PARAM_CI_OFFERANSWER,
  RIL_PARAM_CI_HANDOVERSTATE,
  RIL_PARAM_CI_CALLMODIFICATIONCAUSE,
  RIL_PARAM_CI_RTTMODETYPE,
  RIL_PARAM_CI_RTTCAPINFO,
  RIL_PARAM_CI_RTTACTION,
  RIL_PARAM_CI_ALL
} RILCALLINFOPARAMMASK;
````


## -enum-fields

### -field RIL_PARAM_CI_ID


### -field RIL_PARAM_CI_DIRECTION


### -field RIL_PARAM_CI_STATUS


### -field RIL_PARAM_CI_TYPE


### -field RIL_PARAM_CI_MULTIPARTY


### -field RIL_PARAM_CI_ADDRESS


### -field RIL_PARAM_CI_SUBADDRESS


### -field RIL_PARAM_CI_DESCRIPTION


### -field RIL_PARAM_CI_NUM_PRES_IND


### -field RIL_PARAM_CI_NAME_PRES_IND


### -field RIL_PARAM_CI_FLAGS


### -field RIL_PARAM_CI_DISCONNECTINITIATOR


### -field RIL_PARAM_CI_DISCONNECTREASON


### -field RIL_PARAM_CI_DISCONNECTDETAILS


### -field RIL_PARAM_CI_OFFERANSWER


### -field RIL_PARAM_CI_HANDOVERSTATE


### -field RIL_PARAM_CI_CALLMODIFICATIONCAUSE


### -field RIL_PARAM_CI_RTTMODETYPE


### -field RIL_PARAM_CI_RTTCAPINFO


### -field RIL_PARAM_CI_RTTACTION


### -field RIL_PARAM_CI_ALL


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
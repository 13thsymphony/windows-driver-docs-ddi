---
UID: NE.rilapitypes.RILSUPSVCINFOPARAMMASK
title: RILSUPSVCINFOPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsupsvcinfoparammask_2.htm
old-project: netvista
ms.assetid: 52dd2092-939a-491b-af2d-2ea86eabf99a
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RILSUPSVCINFOPARAMMASK, RILSUPSVCINFOPARAMMASK
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
req.alt-api: RILSUPSVCINFOPARAMMASK
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

# RILSUPSVCINFOPARAMMASK enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax

````
typedef enum _RILSUPSVCINFOPARAMMASK { 
  RIL_PARAM_SSI_FROM_NETWORK,
  RIL_PARAM_SSI_FAILURE_REASON,
  RIL_PARAM_SSI_SUPSVC_ACTION,
  RIL_PARAM_SSI_SUPSVC_TYPE,
  RIL_PARAM_SSI_CALL_FORWARDING_REASON,
  RIL_PARAM_SSI_CALL_BARRING_TYPE,
  RIL_PARAM_SSI_INFOCLASSES,
  RIL_PARAM_SSI_ALPHA_IDENTIFIER,
  RIL_PARAM_SSI_CALL_BARRING_PASSWORD,
  RIL_PARAM_SSI_NEW_CALL_BARRING_PASSWORD,
  RIL_PARAM_SSI_CALL_FORWARDING_SETTINGS,
  RIL_PARAM_SSI_CALLER_ID_SETTINGS,
  RIL_PARAM_SSI_DIALED_ID_SETTINGS,
  RIL_PARAM_SSI_HIDE_ID_SETTINGS,
  RIL_PARAM_SSI_CONNECTED_ID_SETTINGS,
  RIL_PARAM_SSI_SUPSERVICE_DATA,
  RIL_PARAM_SSI_ALL
} RILSUPSVCINFOPARAMMASK;
````


## -enum-fields

### -field RIL_PARAM_SSI_FROM_NETWORK


### -field RIL_PARAM_SSI_FAILURE_REASON


### -field RIL_PARAM_SSI_SUPSVC_ACTION


### -field RIL_PARAM_SSI_SUPSVC_TYPE


### -field RIL_PARAM_SSI_CALL_FORWARDING_REASON


### -field RIL_PARAM_SSI_CALL_BARRING_TYPE


### -field RIL_PARAM_SSI_INFOCLASSES


### -field RIL_PARAM_SSI_ALPHA_IDENTIFIER


### -field RIL_PARAM_SSI_CALL_BARRING_PASSWORD


### -field RIL_PARAM_SSI_NEW_CALL_BARRING_PASSWORD


### -field RIL_PARAM_SSI_CALL_FORWARDING_SETTINGS


### -field RIL_PARAM_SSI_CALLER_ID_SETTINGS


### -field RIL_PARAM_SSI_DIALED_ID_SETTINGS


### -field RIL_PARAM_SSI_HIDE_ID_SETTINGS


### -field RIL_PARAM_SSI_CONNECTED_ID_SETTINGS


### -field RIL_PARAM_SSI_SUPSERVICE_DATA


### -field RIL_PARAM_SSI_ALL


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
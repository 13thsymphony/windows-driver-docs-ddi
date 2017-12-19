---
UID: NE.ntddrilapitypes.RILUNSOLICITEDSSINFOPARAMMASK
title: RILUNSOLICITEDSSINFOPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilunsolicitedssinfoparammask.htm
old-project: NetVista
ms.assetid: 41cf5add-4cad-41ed-ba9c-6bfba56a9f65
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RILUNSOLICITEDSSINFOPARAMMASK, RILUNSOLICITEDSSINFOPARAMMASK
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
req.alt-api: RILUNSOLICITEDSSINFOPARAMMASK
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

# RILUNSOLICITEDSSINFOPARAMMASK enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef enum _RILUNSOLICITEDSSINFOPARAMMASK { 
  RIL_PARAM_UNSSS_ID,
  RIL_PARAM_UNSSS_NOTIFICATIONCODE,
  RIL_PARAM_UNSSS_ADDRESS,
  RIL_PARAM_UNSSS_SUBADDR,
  RIL_PARAM_UNSSS_CUGINDEX,
  RIL_PARAM_UNSSS_HISTLENGTH,
  RIL_PARAM_UNSSS_HISTINFO,
  RIL_PARAM_UNSSS_ALL
} RILUNSOLICITEDSSINFOPARAMMASK;
````


## -enum-fields

### -field RIL_PARAM_UNSSS_ID


### -field RIL_PARAM_UNSSS_NOTIFICATIONCODE


### -field RIL_PARAM_UNSSS_ADDRESS


### -field RIL_PARAM_UNSSS_SUBADDR


### -field RIL_PARAM_UNSSS_CUGINDEX


### -field RIL_PARAM_UNSSS_HISTLENGTH


### -field RIL_PARAM_UNSSS_HISTINFO


### -field RIL_PARAM_UNSSS_ALL


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
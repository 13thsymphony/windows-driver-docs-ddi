---
UID: NE.rilapitypes.RILCALLFORWARDINGSETTINGSPARAMMASK
title: RILCALLFORWARDINGSETTINGSPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallforwardingsettingsparammask_2.htm
old-project: NetVista
ms.assetid: 4db4e6fe-1faf-4109-95aa-e2e5bf3b0dd6
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RILCALLFORWARDINGSETTINGSPARAMMASK, RILCALLFORWARDINGSETTINGSPARAMMASK
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
req.alt-api: RILCALLFORWARDINGSETTINGSPARAMMASK
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

# RILCALLFORWARDINGSETTINGSPARAMMASK enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef enum _RILCALLFORWARDINGSETTINGSPARAMMASK { 
  RIL_PARAM_CFS_INFOCLASSES,
  RIL_PARAM_CFS_ADDRESS,
  RIL_PARAM_CFS_SUBADDRESS,
  RIL_PARAM_CFS_DELAYTIME,
  RIL_PARAM_CFS_ALL
} RILCALLFORWARDINGSETTINGSPARAMMASK;
````


## -enum-fields

### -field RIL_PARAM_CFS_INFOCLASSES


### -field RIL_PARAM_CFS_ADDRESS


### -field RIL_PARAM_CFS_SUBADDRESS


### -field RIL_PARAM_CFS_DELAYTIME


### -field RIL_PARAM_CFS_ALL


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
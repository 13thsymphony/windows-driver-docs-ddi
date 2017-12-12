---
UID: NE.ntddrilapitypes.RILSYSTEMSELECTIONPREFSPARAMMASK
title: RILSYSTEMSELECTIONPREFSPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsystemselectionprefsparammask.htm
old-project: netvista
ms.assetid: 69560c05-8a54-4a67-a441-2b3c2ec4c332
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: RILSYSTEMSELECTIONPREFSPARAMMASK, RILSYSTEMSELECTIONPREFSPARAMMASK
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
req.alt-api: RILSYSTEMSELECTIONPREFSPARAMMASK
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

# RILSYSTEMSELECTIONPREFSPARAMMASK enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef enum _RILSYSTEMSELECTIONPREFSPARAMMASK { 
  RIL_PARAM_SSP_SYSTEMTYPES,
  RIL_PARAM_SSP_MODE,
  RIL_PARAM_SSP_PLMNINFO,
  RIL_PARAM_SSP_ROAMINGMODE,
  RIL_PARAM_SSP_ACQUISITIONORDERSIZE,
  RIL_PARAM_SSP_ACQUISITIONORDER,
  RIL_PARAM_SSP_ALL
} RILSYSTEMSELECTIONPREFSPARAMMASK;
````


## -enum-fields

### -field RIL_PARAM_SSP_SYSTEMTYPES


### -field RIL_PARAM_SSP_MODE


### -field RIL_PARAM_SSP_PLMNINFO


### -field RIL_PARAM_SSP_ROAMINGMODE


### -field RIL_PARAM_SSP_ACQUISITIONORDERSIZE


### -field RIL_PARAM_SSP_ACQUISITIONORDER


### -field RIL_PARAM_SSP_ALL


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
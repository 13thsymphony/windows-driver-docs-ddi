---
UID: NS.NTDDRILAPITYPES.RILSETDMPROFILECONFIGINFOPARAMS
title: RILSETDMPROFILECONFIGINFOPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsetdmprofileconfiginfoparams.htm
old-project: NetVista
ms.assetid: d485f00e-5fa6-4a01-83fe-78e59a8d8fcb
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RILSETDMPROFILECONFIGINFOPARAMS, RILSETDMPROFILECONFIGINFOPARAMS, LPRILSETDMPROFILECONFIGINFOPARAMS, *LPRILSETDMPROFILECONFIGINFOPARAMS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILSETDMPROFILECONFIGINFOPARAMS
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

# RILSETDMPROFILECONFIGINFOPARAMS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILSETDMPROFILECONFIGINFOPARAMS {
  DWORD                 dwExecutor;
  RILDMCONFIGINFOITEM   dwConfigItem;
  RILDMCONFIGINFOVALUE  rciValue;
} RILSETDMPROFILECONFIGINFOPARAMS, RILSETDMPROFILECONFIGINFOPARAMS;
````


## -struct-fields

### -field dwExecutor


### -field dwConfigItem


### -field rciValue


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
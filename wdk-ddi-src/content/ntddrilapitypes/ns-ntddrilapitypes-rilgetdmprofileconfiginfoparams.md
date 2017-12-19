---
UID: NS.NTDDRILAPITYPES.RILGETDMPROFILECONFIGINFOPARAMS
title: RILGETDMPROFILECONFIGINFOPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgetdmprofileconfiginfoparams.htm
old-project: NetVista
ms.assetid: df62bc19-81c7-4d80-88ed-5e8a8438d269
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RILGETDMPROFILECONFIGINFOPARAMS, LPRILGETDMPROFILECONFIGINFOPARAMS, *LPRILGETDMPROFILECONFIGINFOPARAMS, RILGETDMPROFILECONFIGINFOPARAMS
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
req.alt-api: RILGETDMPROFILECONFIGINFOPARAMS
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

# RILGETDMPROFILECONFIGINFOPARAMS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILGETDMPROFILECONFIGINFOPARAMS {
  DWORD                dwExecutor;
  RILDMCONFIGINFOITEM  dwConfigItem;
} RILGETDMPROFILECONFIGINFOPARAMS, RILGETDMPROFILECONFIGINFOPARAMS;
````


## -struct-fields

### -field dwExecutor


### -field dwConfigItem


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
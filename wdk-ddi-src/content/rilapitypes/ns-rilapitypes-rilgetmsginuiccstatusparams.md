---
UID: NS:rilapitypes.RILGETMSGINUICCSTATUSPARAMS
title: RILGETMSGINUICCSTATUSPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgetmsginuiccstatusparams_2.htm
old-project: netvista
ms.assetid: 9e51f87a-42ae-4ee7-ae34-b49b40109e8b
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: RILGETMSGINUICCSTATUSPARAMS, *LPRILGETMSGINUICCSTATUSPARAMS, RILGETMSGINUICCSTATUSPARAMS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILGETMSGINUICCSTATUSPARAMS
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
req.typenames: *LPRILGETMSGINUICCSTATUSPARAMS, RILGETMSGINUICCSTATUSPARAMS
req.product: Windows 10 or later.
---

# RILGETMSGINUICCSTATUSPARAMS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILGETMSGINUICCSTATUSPARAMS {
  HUICCAPP  hUiccApp;
  DWORD     dwIndex;
} RILGETMSGINUICCSTATUSPARAMS, RILGETMSGINUICCSTATUSPARAMS;
````


## -struct-fields

### -field hUiccApp


### -field dwIndex


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
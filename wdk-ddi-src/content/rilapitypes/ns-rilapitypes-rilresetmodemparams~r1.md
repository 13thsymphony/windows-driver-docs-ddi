---
UID: NS.RILAPITYPES.RILRESETMODEMPARAMS~R1
title: RILRESETMODEMPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilresetmodemparams_2.htm
old-project: NetVista
ms.assetid: 5888ba1d-b9f2-41c3-a39d-6a2fffc593fd
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RILRESETMODEMPARAMS, *LPRILRESETMODEMPARAMS, RILRESETMODEMPARAMS
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
req.alt-api: RILRESETMODEMPARAMS
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

# RILRESETMODEMPARAMS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILRESETMODEMPARAMS {
  DWORD                       dwResetKind;
  DWORD                       dwNumberOfConfigItems;
  RILRESETMODEMCONFIGITEM [1] rmciModemConfigItems;
} RILRESETMODEMPARAMS, RILRESETMODEMPARAMS;
````


## -struct-fields

### -field dwResetKind


### -field dwNumberOfConfigItems


### -field rmciModemConfigItems


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
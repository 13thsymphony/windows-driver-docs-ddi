---
UID: NS.NTDDRILAPITYPES.RILUICCAPPDATACHANGE
title: RILUICCAPPDATACHANGE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccappdatachange.htm
old-project: netvista
ms.assetid: a551f469-96f4-42cf-826d-3557cc13ce29
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: RILUICCAPPDATACHANGE, *LPRILUICCAPPDATACHANGE, RILUICCAPPDATACHANGE
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
req.alt-api: RILUICCAPPDATACHANGE
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

# RILUICCAPPDATACHANGE structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILUICCAPPDATACHANGE {
  DWORD                     cbSize;
  HUICCAPP                  hUiccApp;
  RILUICCAPPDATACHANGEENUM  dwDataChange;
} RILUICCAPPDATACHANGE, RILUICCAPPDATACHANGE;
````


## -struct-fields

### -field cbSize


### -field hUiccApp


### -field dwDataChange


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
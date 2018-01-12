---
UID: NS:rilapitypes.RILUICCRESPONSE
title: RILUICCRESPONSE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccresponse_2.htm
old-project: netvista
ms.assetid: c3d3481e-a0db-492d-8fc3-6bdcfa26f4c4
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: RILUICCRESPONSE, RILUICCRESPONSE, *LPRILUICCRESPONSE
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
req.alt-api: RILUICCRESPONSE
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
req.typenames: RILUICCRESPONSE, *LPRILUICCRESPONSE
req.product: Windows 10 or later.
---

# RILUICCRESPONSE structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILUICCRESPONSE {
  DWORD    cbSize;
  DWORD    dwParams;
  DWORD    dwStatusWord1;
  DWORD    dwStatusWord2;
  DWORD    dwResponseSize;
  BYTE [1] pbResponse;
} RILUICCRESPONSE, RILUICCRESPONSE;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field dwStatusWord1


### -field dwStatusWord2


### -field dwResponseSize


### -field pbResponse


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
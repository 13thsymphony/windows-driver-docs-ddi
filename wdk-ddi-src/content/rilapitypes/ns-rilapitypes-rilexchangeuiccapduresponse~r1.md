---
UID: NS.RILAPITYPES.RILEXCHANGEUICCAPDURESPONSE~R1
title: RILEXCHANGEUICCAPDURESPONSE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilexchangeuiccapduresponse_2.htm
old-project: netvista
ms.assetid: c9e3a4b3-2ce2-4f90-8be2-01d9870cc982
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: RILEXCHANGEUICCAPDURESPONSE, RILEXCHANGEUICCAPDURESPONSE, *LPRILEXCHANGEUICCAPDURESPONSE
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
req.alt-api: RILEXCHANGEUICCAPDURESPONSE
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

# RILEXCHANGEUICCAPDURESPONSE structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILEXCHANGEUICCAPDURESPONSE {
  DWORD    cbSize;
  DWORD    dwParams;
  DWORD    dwResponseAPDULength;
  BYTE [1] bResponseAPDU;
} RILEXCHANGEUICCAPDURESPONSE, RILEXCHANGEUICCAPDURESPONSE;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field dwResponseAPDULength


### -field bResponseAPDU


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
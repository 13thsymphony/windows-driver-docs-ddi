---
UID: NS.RILAPITYPES.RILIMSI~R1
title: RILIMSI
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilimsi_2.htm
old-project: NetVista
ms.assetid: 0ec6eead-debb-4901-a099-6ecef19bc4c9
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RILIMSI, *LPRILIMSI, RILIMSI
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
req.alt-api: RILIMSI
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

# RILIMSI structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILIMSI {
  DWORD                  cbSize;
  DWORD                  dwParams;
  WCHAR [MAXLENGTH_IMSI] wszImsi;
  DWORD                  dwMcc;
  DWORD                  dwMnc;
} RILIMSI, RILIMSI;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field wszImsi


### -field dwMcc


### -field dwMnc


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
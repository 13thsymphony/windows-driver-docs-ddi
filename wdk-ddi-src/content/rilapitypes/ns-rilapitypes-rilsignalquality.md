---
UID: NS.RILAPITYPES.RILSIGNALQUALITY
title: RILSIGNALQUALITY
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsignalquality_2.htm
old-project: netvista
ms.assetid: cc5bf370-3996-46de-b27d-8a390a6f407e
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: RILSIGNALQUALITY, RILSIGNALQUALITY, *LPRILSIGNALQUALITY
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
req.alt-api: RILSIGNALQUALITY
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

# RILSIGNALQUALITY structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILSIGNALQUALITY {
  DWORD  cbSize;
  DWORD  dwParams;
  DWORD  dwExecutor;
  DWORD  dwSystemType;
  int    nNumSignalBars;
  int    nSignalStrength;
  int    nSNRStrength;
} RILSIGNALQUALITY, RILSIGNALQUALITY;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field dwExecutor


### -field dwSystemType


### -field nNumSignalBars


### -field nSignalStrength


### -field nSNRStrength


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
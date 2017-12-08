---
UID: NS.NTDDRILAPITYPES.RILADDITIONALNUMBERSTRINGUPDATE
title: RILADDITIONALNUMBERSTRINGUPDATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riladditionalnumberstringupdate.htm
old-project: netvista
ms.assetid: 43fe1e25-be15-4f7a-8ecf-e4492235c6c2
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RILADDITIONALNUMBERSTRINGUPDATE, RILADDITIONALNUMBERSTRINGUPDATE, *LPRILADDITIONALNUMBERSTRINGUPDATE
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
req.alt-api: RILADDITIONALNUMBERSTRINGUPDATE
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

# RILADDITIONALNUMBERSTRINGUPDATE structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax

````
typedef struct _RILADDITIONALNUMBERSTRINGUPDATE {
  DWORD                     cbSize;
  HUICCAPP                  hUiccApp;
  RILPHONEBOOKANSOPERATION  dwOpType;
  DWORD                     dwNumId;
  WCHAR [256]               wszText;
} RILADDITIONALNUMBERSTRINGUPDATE, RILADDITIONALNUMBERSTRINGUPDATE;
````


## -struct-fields

### -field cbSize


### -field hUiccApp


### -field dwOpType


### -field dwNumId


### -field wszText


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
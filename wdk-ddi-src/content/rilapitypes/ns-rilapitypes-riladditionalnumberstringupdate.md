---
UID: NS:rilapitypes.RILADDITIONALNUMBERSTRINGUPDATE
title: RILADDITIONALNUMBERSTRINGUPDATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riladditionalnumberstringupdate_2.htm
old-project: netvista
ms.assetid: b2675395-08b6-44e6-8052-1fdd7b693c31
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: RILADDITIONALNUMBERSTRINGUPDATE, *LPRILADDITIONALNUMBERSTRINGUPDATE, RILADDITIONALNUMBERSTRINGUPDATE
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
req.alt-api: RILADDITIONALNUMBERSTRINGUPDATE
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
req.typenames: *LPRILADDITIONALNUMBERSTRINGUPDATE, RILADDITIONALNUMBERSTRINGUPDATE
req.product: Windows 10 or later.
---

# RILADDITIONALNUMBERSTRINGUPDATE structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILADDITIONALNUMBERSTRINGUPDATE {
  DWORD                           cbSize;
  HUICCAPP                        hUiccApp;
  RILPHONEBOOKANSOPERATION        dwOpType;
  DWORD                           dwNumId;
  WCHAR [MAXLENGTH_PHONEBOOKTEXT] wszText;
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
<dt>Rilapitypes.h</dt>
</dl>
</td>
</tr>
</table>
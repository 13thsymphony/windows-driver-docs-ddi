---
UID: NS.RILAPITYPES.RILSETSMSCPARAMS~R1
title: RILSETSMSCPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsetsmscparams_2.htm
old-project: NetVista
ms.assetid: 87c5bb45-f29d-434c-abef-acbf05c9515e
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RILSETSMSCPARAMS, *LPRILSETSMSCPARAMS, RILSETSMSCPARAMS
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
req.alt-api: RILSETSMSCPARAMS
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

# RILSETSMSCPARAMS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILSETSMSCPARAMS {
  HUICCAPP    hUiccApp;
  RILADDRESS  raSvcCtrAddress;
} RILSETSMSCPARAMS, RILSETSMSCPARAMS;
````


## -struct-fields

### -field hUiccApp


### -field raSvcCtrAddress


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
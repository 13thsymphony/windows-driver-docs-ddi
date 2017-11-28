---
UID: NS.rilapitypes.RILMESSAGESTORAGEFULL
title: RILMESSAGESTORAGEFULL
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmessagestoragefull_2.htm
old-project: netvista
ms.assetid: fa0e5c57-7ceb-442d-95ea-971824c88298
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: RILMESSAGESTORAGEFULL, RILMESSAGESTORAGEFULL
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
req.alt-api: RILMESSAGESTORAGEFULL
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
req.iface: 
req.product: Windows 10 or later.
---

# RILMESSAGESTORAGEFULL structure



## -description
<p>This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. </p>


## -syntax

````
typedef struct _RILMESSAGESTORAGEFULL {
  DWORD     cbSize;
  DWORD     dwExecutor;
  HUICCAPP  hUiccApp;
} RILMESSAGESTORAGEFULL, RILMESSAGESTORAGEFULL;
````


## -struct-fields
<dl>

### -field <b>cbSize</b>

<dd></dd>

### -field <b>dwExecutor</b>

<dd></dd>

### -field <b>hUiccApp</b>

<dd></dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Rilapitypes.h</dt>
</dl>
</td>
</tr>
</table>
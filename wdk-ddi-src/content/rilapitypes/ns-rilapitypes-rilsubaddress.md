---
UID: NS.RILAPITYPES.RILSUBADDRESS
title: RILSUBADDRESS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsubaddress_2.htm
old-project: netvista
ms.assetid: fa8f7b01-a767-4713-b1e3-7417efb7db47
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: RILSUBADDRESS, RILSUBADDRESS, *LPRILSUBADDRESS
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
req.alt-api: RILSUBADDRESS
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

# RILSUBADDRESS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILSUBADDRESS {
  DWORD                     cbSize;
  DWORD                     dwParams;
  RILSUBADDRESSTYPE         dwType;
  WCHAR [MAXLENGTH_SUBADDR] wszSubAddress;
} RILSUBADDRESS, RILSUBADDRESS;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field dwType


### -field wszSubAddress


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
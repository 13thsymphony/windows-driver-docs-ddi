---
UID: NF.printoem.OEMTTYGetInfo
title: OEMTTYGetInfo function
author: windows-driver-content
description: OEMTTYGetInfo function
old-location: print\oemttygetinfo.htm
old-project: print
ms.assetid: 9b6fcd4e-6472-4e46-b0b7-dd1279e534d0
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: OEMTTYGetInfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: printoem.h
req.include-header: Printoem.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: OEMTTYGetInfo
req.alt-loc: printoem.h
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

# OEMTTYGetInfo function



## -description

## -syntax

````
INT APIENTRY OEMTTYGetInfo(
        PDEVOBJ                      pdevobj,
        DWORD                        dwInfoIndex,
  _Out_ _writes_bytes_(dwSize) PVOID pOutputBuf,
        DWORD                        dwSize,
  _Out_ DWORD                        *pcbcNeeded
);
````


## -parameters

### -param pdevobj 


### -param dwInfoIndex 


### -param pOutputBuf [out]


### -param dwSize 


### -param pcbcNeeded [out]


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Printoem.h (include Printoem.h)</dt>
</dl>
</td>
</tr>
</table>
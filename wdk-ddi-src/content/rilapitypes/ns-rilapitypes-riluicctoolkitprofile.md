---
UID: NS.RILAPITYPES.RILUICCTOOLKITPROFILE
title: RILUICCTOOLKITPROFILE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluicctoolkitprofile_2.htm
old-project: NetVista
ms.assetid: 8d8a6c85-474c-4e86-99a9-ac113edbe7b3
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RILUICCTOOLKITPROFILE, *LPRILUICCTOOLKITPROFILE, RILUICCTOOLKITPROFILE
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
req.alt-api: RILUICCTOOLKITPROFILE
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

# RILUICCTOOLKITPROFILE structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILUICCTOOLKITPROFILE {
  DWORD    cbSize;
  DWORD    dwProfileSize;
  BYTE [1] bProfile;
} RILUICCTOOLKITPROFILE, RILUICCTOOLKITPROFILE;
````


## -struct-fields

### -field cbSize


### -field dwProfileSize


### -field bProfile


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
---
UID: NS:ntddrilapitypes.RILUICCFILES
title: RILUICCFILES
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccfiles.htm
old-project: netvista
ms.assetid: a29f2ff6-1c15-4313-b3a5-73fb8d40d2d7
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: RILUICCFILES, RILUICCFILES, *LPRILUICCFILES
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
req.alt-api: RILUICCFILES
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
req.typenames: RILUICCFILES, *LPRILUICCFILES
---

# RILUICCFILES structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILUICCFILES {
  DWORD               cbSize;
  DWORD               dwNumFiles;
  RILUICCFILEPATH [1] filePath;
} RILUICCFILES, RILUICCFILES;
````


## -struct-fields

### -field cbSize


### -field dwNumFiles


### -field filePath


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
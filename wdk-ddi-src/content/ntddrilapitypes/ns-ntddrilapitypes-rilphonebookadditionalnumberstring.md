---
UID: NS.NTDDRILAPITYPES.RILPHONEBOOKADDITIONALNUMBERSTRING
title: RILPHONEBOOKADDITIONALNUMBERSTRING
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilphonebookadditionalnumberstring.htm
old-project: netvista
ms.assetid: 1d201c4d-606d-4461-ad3d-df48d3455724
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: RILPHONEBOOKADDITIONALNUMBERSTRING, *LPRILPHONEBOOKADDITIONALNUMBERSTRING, RILPHONEBOOKADDITIONALNUMBERSTRING
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
req.alt-api: RILPHONEBOOKADDITIONALNUMBERSTRING
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

# RILPHONEBOOKADDITIONALNUMBERSTRING structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILPHONEBOOKADDITIONALNUMBERSTRING {
  DWORD       cbSize;
  DWORD       dwNumId;
  WCHAR [256] wszText;
} RILPHONEBOOKADDITIONALNUMBERSTRING, RILPHONEBOOKADDITIONALNUMBERSTRING;
````


## -struct-fields

### -field cbSize


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
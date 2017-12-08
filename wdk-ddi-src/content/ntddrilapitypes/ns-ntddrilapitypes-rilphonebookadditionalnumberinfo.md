---
UID: NS.NTDDRILAPITYPES.RILPHONEBOOKADDITIONALNUMBERINFO
title: RILPHONEBOOKADDITIONALNUMBERINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilphonebookadditionalnumberinfo.htm
old-project: netvista
ms.assetid: bc4026e5-6613-4787-9218-22d1d3e447c3
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RILPHONEBOOKADDITIONALNUMBERINFO, *LPRILPHONEBOOKADDITIONALNUMBERINFO, RILPHONEBOOKADDITIONALNUMBERINFO
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
req.alt-api: RILPHONEBOOKADDITIONALNUMBERINFO
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

# RILPHONEBOOKADDITIONALNUMBERINFO structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax

````
typedef struct _RILPHONEBOOKADDITIONALNUMBERINFO {
  DWORD                                  cbSize;
  DWORD                                  dwRilPBANSSize;
  RILPHONEBOOKADDITIONALNUMBERSTRING [1] RilPBANS;
} RILPHONEBOOKADDITIONALNUMBERINFO, RILPHONEBOOKADDITIONALNUMBERINFO;
````


## -struct-fields

### -field cbSize


### -field dwRilPBANSSize


### -field RilPBANS


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
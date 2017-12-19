---
UID: NS.NTDDRILAPITYPES.RILSMSMODIFICATIONINFO
title: RILSMSMODIFICATIONINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsmsmodificationinfo.htm
old-project: NetVista
ms.assetid: 8fed32a2-f0a7-4462-b8bb-b01c9cccf6b7
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RILSMSMODIFICATIONINFO, RILSMSMODIFICATIONINFO, LPRILSMSMODIFICATIONINFO, *LPRILSMSMODIFICATIONINFO
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
req.alt-api: RILSMSMODIFICATIONINFO
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

# RILSMSMODIFICATIONINFO structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILSMSMODIFICATIONINFO {
  DWORD               cbSize;
  DWORD               dwParams;
  DWORD               dwExecutor;
  DWORD               dwModificationType;
  RILADDRESS          raAddress;
  RILALPHAIDENTIFIER  aiIdentifier;
} RILSMSMODIFICATIONINFO, RILSMSMODIFICATIONINFO;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field dwExecutor


### -field dwModificationType


### -field raAddress


### -field aiIdentifier


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
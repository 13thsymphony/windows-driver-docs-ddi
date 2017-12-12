---
UID: NS.NTDDRILAPITYPES.RILMESSAGEIN_V1
title: RILMESSAGEIN_V1
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmessagein_v1.htm
old-project: netvista
ms.assetid: c9de99e4-556c-4b3b-a442-53fc52553d3d
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: RILMESSAGEIN_V1, RILMESSAGEIN_V1
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
req.alt-api: RILMESSAGEIN_V1
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

# RILMESSAGEIN_V1 structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILMESSAGEIN_V1 {
  DWORD       cbSize;
  DWORD       dwExecutor;
  HUICCAPP    hUiccApp;
  DWORD       dwAckID;
  RILMESSAGE  rm;
} RILMESSAGEIN_V1, RILMESSAGEIN_V1;
````


## -struct-fields

### -field cbSize


### -field dwExecutor


### -field hUiccApp


### -field dwAckID


### -field rm


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
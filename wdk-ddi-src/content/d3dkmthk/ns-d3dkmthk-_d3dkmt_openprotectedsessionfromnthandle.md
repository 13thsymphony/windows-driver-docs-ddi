---
UID: NS.D3DKMTHK._D3DKMT_OPENPROTECTEDSESSIONFROMNTHANDLE
title: _D3DKMT_OPENPROTECTEDSESSIONFROMNTHANDLE
author: windows-driver-content
description: Used to open a protected session from the NT handle.
old-location: display\d3dkmt-openprotectedsessionfromnthandle.htm
old-project: display
ms.assetid: 15937864-c6ef-4c86-b957-87c7afe1cd94
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _D3DKMT_OPENPROTECTEDSESSIONFROMNTHANDLE, D3DKMT_OPENPROTECTEDSESSIONFROMNTHANDLE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_OPENPROTECTEDSESSIONFROMNTHANDLE
req.alt-loc: d3dkmthk.h
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

# _D3DKMT_OPENPROTECTEDSESSIONFROMNTHANDLE structure



## -description
Used to open a protected session from the NT handle.



## -syntax

````
typedef struct _D3DKMT_OPENPROTECTEDSESSIONFROMNTHANDLE {
  HANDLE        hNtHandle;
  D3DKMT_HANDLE hHandle;
} D3DKMT_OPENPROTECTEDSESSIONFROMNTHANDLE;
````


## -struct-fields

### -field hNtHandle

The protected NT session handle.


### -field hHandle

The protected kernel session handle.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmthk.h</dt>
</dl>
</td>
</tr>
</table>
---
UID: NS.D3DKMTHK._D3DKMT_DESTROYPROTECTEDSESSION
title: _D3DKMT_DESTROYPROTECTEDSESSION
author: windows-driver-content
description: Holds information to destroy a protected session.
old-location: display\d3dkmt-destroyprotectedsession.htm
old-project: display
ms.assetid: 371e0353-3e4d-4688-95cf-d5f24b2ed7b3
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _D3DKMT_DESTROYPROTECTEDSESSION, D3DKMT_DESTROYPROTECTEDSESSION
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
req.alt-api: D3DKMT_DESTROYPROTECTEDSESSION
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

# _D3DKMT_DESTROYPROTECTEDSESSION structure



## -description
Holds information to destroy a protected session.


## -syntax

````
typedef struct _D3DKMT_DESTROYPROTECTEDSESSION {
  D3DKMT_HANDLE hHandle;
} D3DKMT_DESTROYPROTECTEDSESSION;
````


## -struct-fields

### -field hHandle

The protected session handle.

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
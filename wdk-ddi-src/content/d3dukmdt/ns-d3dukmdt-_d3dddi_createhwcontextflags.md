---
UID: NS.D3DUKMDT._D3DDDI_CREATEHWCONTEXTFLAGS
title: _D3DDDI_CREATEHWCONTEXTFLAGS
author: windows-driver-content
description: A structure used to create hardware context flags.
old-location: display\d3dddi_createhwcontextflags.htm
old-project: display
ms.assetid: 429A1C54-14F0-4E50-B0D6-BB73FCFD1904
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _D3DDDI_CREATEHWCONTEXTFLAGS, D3DDDI_CREATEHWCONTEXTFLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDI_CREATEHWCONTEXTFLAGS
req.alt-loc: d3dukmdt.h
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

# _D3DDDI_CREATEHWCONTEXTFLAGS structure



## -description
A structure used to create hardware context flags.


## -syntax

````
typedef struct _D3DDDI_CREATEHWCONTEXTFLAGS {
  union {
    struct {
      UINT Reserved  :32;
    };
    UINT Value;
  };
} D3DDDI_CREATEHWCONTEXTFLAGS;
````


## -struct-fields

### -field Reserved

This value is reserved for system use.

### -field Value

This value is used to operate over the members collectively.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>D3dukmdt.h</dt>
</dl>
</td>
</tr>
</table>
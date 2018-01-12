---
UID: NS:d3dumddi._D3DDDICB_DESTROYHWCONTEXT
title: _D3DDDICB_DESTROYHWCONTEXT
author: windows-driver-content
description: A structure that holds information to destroy a hardware context.
old-location: display\d3dddicb_destroyhwcontext.htm
old-project: display
ms.assetid: 9040AEAF-3F66-4F76-B9CD-36370BC2F5B6
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DDDICB_DESTROYHWCONTEXT, D3DDDICB_DESTROYHWCONTEXT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDICB_DESTROYHWCONTEXT
req.alt-loc: d3dumddi.h
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
req.typenames: D3DDDICB_DESTROYHWCONTEXT
---

# _D3DDDICB_DESTROYHWCONTEXT structure



## -description
A structure that holds information to destroy a hardware context.



## -syntax

````
typedef struct _D3DDDICB_DESTROYHWCONTEXT {
  HANDLE hHwContext;
} D3DDDICB_DESTROYHWCONTEXT;
````


## -struct-fields

### -field hHwContext

Handle to the context to destroy.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dumddi.h</dt>
</dl>
</td>
</tr>
</table>
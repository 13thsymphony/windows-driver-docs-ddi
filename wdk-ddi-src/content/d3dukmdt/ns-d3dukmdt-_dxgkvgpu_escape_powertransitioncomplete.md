---
UID: NS:d3dukmdt._DXGKVGPU_ESCAPE_POWERTRANSITIONCOMPLETE
title: _DXGKVGPU_ESCAPE_POWERTRANSITIONCOMPLETE
author: windows-driver-content
description: Indicates that a power transition has completed.
old-location: display\dxgkvgpu_escape_powertransitioncomplete.htm
old-project: display
ms.assetid: 39800C47-95EB-4867-8FEE-E94EA3F6F68C
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGKVGPU_ESCAPE_POWERTRANSITIONCOMPLETE, DXGKVGPU_ESCAPE_POWERTRANSITIONCOMPLETE
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
req.alt-api: DXGKVGPU_ESCAPE_POWERTRANSITIONCOMPLETE
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
req.typenames: DXGKVGPU_ESCAPE_POWERTRANSITIONCOMPLETE
---

# _DXGKVGPU_ESCAPE_POWERTRANSITIONCOMPLETE structure



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

Indicates that a power transition has completed.



## -syntax

````
typedef struct _DXGKVGPU_ESCAPE_POWERTRANSITIONCOMPLETE {
  DXGKVGPU_ESCAPE_HEAD Header;
  UINT                 PowerState;
} DXGKVGPU_ESCAPE_POWERTRANSITIONCOMPLETE;
````


## -struct-fields

### -field Header

The header that is being operated over.


### -field PowerState

Indicates the power state to transition to.


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
---
UID: NS:d3dkmthk._D3DKMT_SETVIDPNSOURCEOWNER2
title: _D3DKMT_SETVIDPNSOURCEOWNER2
author: windows-driver-content
description: Used to set the VidPN source owner.
old-location: display\d3dkmt-setvidpnsourceowner2.htm
old-project: display
ms.assetid: 6a6477db-23ad-42ad-b1cb-d81c7be4cf38
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DKMT_SETVIDPNSOURCEOWNER2, D3DKMT_SETVIDPNSOURCEOWNER2
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
req.alt-api: D3DKMT_SETVIDPNSOURCEOWNER2
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
req.typenames: D3DKMT_SETVIDPNSOURCEOWNER2
---

# _D3DKMT_SETVIDPNSOURCEOWNER2 structure



## -description
Used to set the VidPN source owner.



## -syntax

````
typedef struct _D3DKMT_SETVIDPNSOURCEOWNER2 {
  D3DKMT_SETVIDPNSOURCEOWNER1 Version1;
  HANDLE const*               *pVidPnSourceNtHandles;
} D3DKMT_SETVIDPNSOURCEOWNER2;
````


## -struct-fields

### -field Version1

The previous method used to set the VidPN source owner.


### -field pVidPnSourceNtHandles

A handle to the VidPN source owner handles.


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
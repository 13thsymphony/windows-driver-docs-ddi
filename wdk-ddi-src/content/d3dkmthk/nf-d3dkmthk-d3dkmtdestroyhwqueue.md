---
UID: NF.d3dkmthk.D3DKMTDestroyHwQueue
title: D3DKMTDestroyHwQueue function
author: windows-driver-content
description: Used to destroy a hardware queue.
old-location: display\d3dkmtdestroyhwqueue.htm
old-project: display
ms.assetid: 30687710-A813-4D3C-8612-9236D34EB9EB
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: D3DKMTDestroyHwQueue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMTDestroyHwQueue
req.alt-loc: tbd
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Tbd
req.dll: Tbd
req.irql: 
---

# D3DKMTDestroyHwQueue function



## -description
Used to destroy a hardware queue.



## -syntax

````
NTSTATUS APIENTRY D3DKMTDestroyHwQueue(
  _In_ const D3DKMT_DESTROYHWQUEUE *destroyHwContext
);
````


## -parameters

### -param destroyHwContext [in]

A structure holding the information needed to destroy a hardware queue.


## -returns
Returns STATUS_SUCCESS if called successfully. 


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
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Tbd</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>Tbd</dt>
</dl>
</td>
</tr>
</table>
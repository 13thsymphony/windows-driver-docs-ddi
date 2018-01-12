---
UID: NF:d3dkmthk.D3DKMTDestroyHwContext
title: D3DKMTDestroyHwContext function
author: windows-driver-content
description: Used to destroy a hardware context.
old-location: display\d3dkmtdestroyhwcontext.htm
old-project: display
ms.assetid: 832CA7CA-40B3-4D6D-B640-9838B479EC76
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTDestroyHwContext
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
req.alt-api: D3DKMTDestroyHwContext
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
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTDestroyHwContext function



## -description
Used to destroy a hardware context.



## -syntax

````
NTSTATUS APIENTRY D3DKMTDestroyHwContext(
  _In_ const D3DKMT_DESTROYHWCONTEXT *destroyHwContext
);
````


## -parameters

### -param destroyHwContext [in]

A structure holding the information needed to destroy a hardware context.


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
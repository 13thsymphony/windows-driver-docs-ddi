---
UID: NC:d3dumddi.PFND3DDDI_CREATEHWCONTEXTCB
title: PFND3DDDI_CREATEHWCONTEXTCB
author: windows-driver-content
description: A callback to create a new hardware context.
old-location: display\pfnd3dddi_createhwcontextcb.htm
old-project: display
ms.assetid: 989682F3-340E-4F64-BF2D-771D58066EB2
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: PFND3DDDI_CREATEHWCONTEXTCB, PFND3DDDI_CREATEHWCONTEXTCB callback function [Display Devices], d3dumddi/PFND3DDDI_CREATEHWCONTEXTCB, display.pfnd3dddi_createhwcontextcb
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	PFND3DDDI_CREATEHWCONTEXTCB
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_CREATEHWCONTEXTCB callback function
A callback to create a new hardware context.

## Syntax

```
PFND3DDDI_CREATEHWCONTEXTCB Pfnd3dddiCreatehwcontextcb;

HRESULT Pfnd3dddiCreatehwcontextcb(
  HANDLE hDevice,
  D3DDDICB_CREATEHWCONTEXT *
)
{...}
```

## Parameters

`hDevice`

A handle to the device.

`*`




## Return Value

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The call was successfully completed.

</td>
</tr>
</table>
 

This function might also return other HRESULT values.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | d3dumddi.h |
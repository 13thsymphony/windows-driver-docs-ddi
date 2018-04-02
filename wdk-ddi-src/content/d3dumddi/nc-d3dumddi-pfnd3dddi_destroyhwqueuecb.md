---
UID: NC:d3dumddi.PFND3DDDI_DESTROYHWQUEUECB
title: PFND3DDDI_DESTROYHWQUEUECB
author: windows-driver-content
description: A callback to destroy a hardware queue.
old-location: display\pfnd3dddi_destroyhwqueuecb.htm
old-project: display
ms.assetid: F3578E0E-2249-4BC2-B776-E6356D523059
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3DDDI_DESTROYHWQUEUECB, PFND3DDDI_DESTROYHWQUEUECB callback function [Display Devices], d3dumddi/PFND3DDDI_DESTROYHWQUEUECB, display.pfnd3dddi_destroyhwqueuecb
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
-	PFND3DDDI_DESTROYHWQUEUECB
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_DESTROYHWQUEUECB callback function
A callback to destroy a hardware queue.

## Syntax

```
PFND3DDDI_DESTROYHWQUEUECB Pfnd3dddiDestroyhwqueuecb;

HRESULT Pfnd3dddiDestroyhwqueuecb(
  HANDLE hDevice,
  CONST D3DDDICB_DESTROYHWQUEUE *
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
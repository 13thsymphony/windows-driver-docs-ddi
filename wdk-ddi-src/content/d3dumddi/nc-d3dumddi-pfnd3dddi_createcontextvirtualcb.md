---
UID: NC:d3dumddi.PFND3DDDI_CREATECONTEXTVIRTUALCB
title: PFND3DDDI_CREATECONTEXTVIRTUALCB
author: windows-driver-content
description: pfnCreateContextVirtualCb should be used with contexts that support virtual addressing.
old-location: display\pfncreatecontextvirtualcb.htm
old-project: display
ms.assetid: 7787FEDF-E18C-4120-A073-A13933856F57
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3DDDI_CREATECONTEXTVIRTUALCB, d3dumddi/pfnCreateContextVirtualCb, display.pfncreatecontextvirtualcb, pfnCreateContextVirtualCb, pfnCreateContextVirtualCb callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	pfnCreateContextVirtualCb
product:
- Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_CREATECONTEXTVIRTUALCB callback function
<b>pfnCreateContextVirtualCb</b> should be used with contexts that support virtual addressing.

## Syntax

```
PFND3DDDI_CREATECONTEXTVIRTUALCB Pfnd3dddiCreatecontextvirtualcb;

HRESULT Pfnd3dddiCreatecontextvirtualcb(
  HANDLE hDevice,
  D3DDDICB_CREATECONTEXTVIRTUAL *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device.

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
The context was successfully created.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

        Could not allocate memory that was required for the operation to complete.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect.

</td>
</tr>
</table>
 

This function might also return other <b>HRESULT</b> values.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |
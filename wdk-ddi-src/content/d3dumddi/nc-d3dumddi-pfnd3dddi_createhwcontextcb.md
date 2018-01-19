---
UID : NC:d3dumddi.PFND3DDDI_CREATEHWCONTEXTCB
title : PFND3DDDI_CREATEHWCONTEXTCB
author : windows-driver-content
description : A callback to create a new hardware context.
old-location : display\pfnd3dddi_createhwcontextcb.htm
old-project : display
ms.assetid : 989682F3-340E-4F64-BF2D-771D58066EB2
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _DXGK_PTE, DXGK_PTE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : d3dumddi.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : PFND3DDDI_CREATEHWCONTEXTCB
req.alt-loc : d3dumddi.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : DXGK_PTE
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

<dl>
<dt><b>S_OK</b></dt>
</dl>The call was successfully completed.

 

This function might also return other HRESULT values.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dumddi.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |
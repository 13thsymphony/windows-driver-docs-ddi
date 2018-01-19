---
UID : NC:d3dumddi.PFND3DDDI_SUBMITSIGNALSYNCOBJECTSTOHWQUEUECB
title : PFND3DDDI_SUBMITSIGNALSYNCOBJECTSTOHWQUEUECB
author : windows-driver-content
description : A callback to submit a signal command to the hardware queue.
old-location : display\pfnd3dddi_submitsignalsyncobjectstohwqueuecb.htm
old-project : display
ms.assetid : D952A432-7B2C-43AC-9BC4-4335D2F37301
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
req.alt-api : PFND3DDDI_SUBMITSIGNALSYNCOBJECTSTOHWQUEUECB
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


# PFND3DDDI_SUBMITSIGNALSYNCOBJECTSTOHWQUEUECB callback function
A callback to submit a signal command to the hardware queue.

## Syntax

```
PFND3DDDI_SUBMITSIGNALSYNCOBJECTSTOHWQUEUECB Pfnd3dddiSubmitsignalsyncobjectstohwqueuecb;

HRESULT Pfnd3dddiSubmitsignalsyncobjectstohwqueuecb(
  HANDLE hDevice,
  CONST D3DDDICB_SUBMITSIGNALSYNCOBJECTSTOHWQUEUE *
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
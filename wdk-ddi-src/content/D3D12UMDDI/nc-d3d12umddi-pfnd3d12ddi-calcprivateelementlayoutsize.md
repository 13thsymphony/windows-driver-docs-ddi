---
UID: NC.d3d12umddi.PFND3D12DDI_CALCPRIVATEELEMENTLAYOUTSIZE
title: PFND3D12DDI_CALCPRIVATEELEMENTLAYOUTSIZE
author: windows-driver-content
description: 
ms.assetid: d17de504-c0e2-474e-8526-ee6ecbec5732
ms.author: windowsdriverdev
ms.date: 
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.alt-api:
req.alt-loc:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library:
---

# PFND3D12DDI_CALCPRIVATEELEMENTLAYOUTSIZE callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFND3D12DDI_CALCPRIVATEELEMENTLAYOUTSIZE Pfnd3d12ddiCalcprivateelementlayoutsize; 

// Definition

SIZE_T Pfnd3d12ddiCalcprivateelementlayoutsize 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATEELEMENTLAYOUT *
)
{...}

PFND3D12DDI_CALCPRIVATEELEMENTLAYOUTSIZE 


```

## -parameters

### -param D3D12DDI_HDEVICE: 
### -param *: 



## -returns

Returns SIZE_T that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also
---
UID: NC.d3d12umddi.PFND3D12DDI_MAKERESIDENT_0001
title: PFND3D12DDI_MAKERESIDENT_0001
author: windows-driver-content
description: 
ms.assetid: 0153feda-8fb0-44d8-8253-90c552867bee
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

# PFND3D12DDI_MAKERESIDENT_0001 callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFND3D12DDI_MAKERESIDENT_0001 Pfnd3d12ddiMakeresident0001; 

// Definition

HRESULT Pfnd3d12ddiMakeresident0001 
(
	 D3D12DDI_HDEVICE
	D3D12DDIARG_MAKERESIDENT_0001 *
)
{...}

PFND3D12DDI_MAKERESIDENT_0001 


```

## -parameters

### -param D3D12DDI_HDEVICE: 
### -param *: 



## -returns

Returns HRESULT that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also
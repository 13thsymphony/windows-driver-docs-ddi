---
UID: NC.d3d12umddi.PFND3D12DDI_CREATE_RENDER_TARGET_VIEW_0002
title: PFND3D12DDI_CREATE_RENDER_TARGET_VIEW_0002
author: windows-driver-content
description: 
ms.assetid: 9919f24c-2280-4181-8308-9b051805676c
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

# PFND3D12DDI_CREATE_RENDER_TARGET_VIEW_0002 callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFND3D12DDI_CREATE_RENDER_TARGET_VIEW_0002 Pfnd3d12ddiCreateRenderTargetView0002; 

// Definition

VOID Pfnd3d12ddiCreateRenderTargetView0002 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATE_RENDER_TARGET_VIEW_0002 *
	D3D12DDI_CPU_DESCRIPTOR_HANDLE DestDescriptor
)
{...}

PFND3D12DDI_CREATE_RENDER_TARGET_VIEW_0002 


```

## -parameters

### -param D3D12DDI_HDEVICE: 
### -param *: 
### -param DestDescriptor: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also
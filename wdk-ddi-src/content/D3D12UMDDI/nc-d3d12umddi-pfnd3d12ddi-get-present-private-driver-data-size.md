---
UID: NC.d3d12umddi.PFND3D12DDI_GET_PRESENT_PRIVATE_DRIVER_DATA_SIZE
title: PFND3D12DDI_GET_PRESENT_PRIVATE_DRIVER_DATA_SIZE
author: windows-driver-content
description: 
ms.assetid: 9052d776-e905-4ac4-a1b9-779063d45113
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

# PFND3D12DDI_GET_PRESENT_PRIVATE_DRIVER_DATA_SIZE callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFND3D12DDI_GET_PRESENT_PRIVATE_DRIVER_DATA_SIZE Pfnd3d12ddiGetPresentPrivateDriverDataSize; 

// Definition

UINT Pfnd3d12ddiGetPresentPrivateDriverDataSize 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_PRESENT_0001 *
)
{...}

PFND3D12DDI_GET_PRESENT_PRIVATE_DRIVER_DATA_SIZE 


```

## -parameters

### -param D3D12DDI_HDEVICE: 
### -param *: 



## -returns

Returns UINT that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also
---
UID: NC.d3d12umddi.PFND3D12DDI_GETMIPPACKING
title: PFND3D12DDI_GETMIPPACKING
author: windows-driver-content
description: 
ms.assetid: 05a33bac-c517-4a16-bd7a-74babab852ea
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

# PFND3D12DDI_GETMIPPACKING callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFND3D12DDI_GETMIPPACKING Pfnd3d12ddiGetmippacking; 

// Definition

VOID Pfnd3d12ddiGetmippacking 
(
	D3D12DDI_HDEVICE hDevice
	D3D12DDI_HRESOURCE hTiledResource
	UINT *pNumPackedMips
	UINT *pNumTilesForPackedMips
)
{...}

PFND3D12DDI_GETMIPPACKING 


```

## -parameters

### -param hDevice: 
### -param hTiledResource: 
### -param *pNumPackedMips: 
### -param *pNumTilesForPackedMips: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also
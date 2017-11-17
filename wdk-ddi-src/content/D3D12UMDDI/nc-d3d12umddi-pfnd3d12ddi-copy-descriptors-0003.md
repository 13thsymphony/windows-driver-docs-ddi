---
UID: NC.d3d12umddi.PFND3D12DDI_COPY_DESCRIPTORS_0003
title: PFND3D12DDI_COPY_DESCRIPTORS_0003
author: windows-driver-content
description: 
ms.assetid: bf0cae15-771b-4334-89a7-5fc85977848f
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

# PFND3D12DDI_COPY_DESCRIPTORS_0003 callback function

## -description

Implemented by the client driver to ... 

## -prototype

```
//Declaration

PFND3D12DDI_COPY_DESCRIPTORS_0003 Pfnd3d12ddiCopyDescriptors0003; 

// Definition

VOID Pfnd3d12ddiCopyDescriptors0003 
(
	 D3D12DDI_HDEVICE
	UINT NumDestDescriptorRanges
	CONST D3D12DDI_CPU_DESCRIPTOR_HANDLE *pDestDescriptorRangeStarts
	CONST UINT *pDestDescriptorRangeSizes
	UINT NumSrcDescriptorRanges
	CONST D3D12DDI_CPU_DESCRIPTOR_HANDLE *pSrcDescriptorRangeStarts
	CONST UINT *pSrcDescriptorRangeSizes
	D3D12DDI_DESCRIPTOR_HEAP_TYPE DescriptorHeapsType
)
{...}

PFND3D12DDI_COPY_DESCRIPTORS_0003 


```

## -parameters

### -param D3D12DDI_HDEVICE: 
### -param NumDestDescriptorRanges: 
### -param *pDestDescriptorRangeStarts: 
### -param *pDestDescriptorRangeSizes: 
### -param NumSrcDescriptorRanges: 
### -param *pSrcDescriptorRangeStarts: 
### -param *pSrcDescriptorRangeSizes: 
### -param DescriptorHeapsType: 



## -returns

Returns VOID that ...

## -remarks

Register your implementation of this callback function by setting the appropriate member of <!-- REPLACE ME --> and then calling <!-- REPLACE ME -->.


## -see-also
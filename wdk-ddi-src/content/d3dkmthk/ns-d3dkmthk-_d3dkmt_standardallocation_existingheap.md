---
UID : NS:d3dkmthk._D3DKMT_STANDARDALLOCATION_EXISTINGHEAP
title : _D3DKMT_STANDARDALLOCATION_EXISTINGHEAP
author : windows-driver-content
description : Holds information about the existing heap.
old-location : display\d3dkmt-standardallocation-existingheap.htm
old-project : display
ms.assetid : 7e97fb29-64a7-4fb5-b07e-a9810499cf1b
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _D3DKMT_STANDARDALLOCATION_EXISTINGHEAP, D3DKMT_STANDARDALLOCATION_EXISTINGHEAP structure [Display Devices], D3DKMT_STANDARDALLOCATION_EXISTINGHEAP, display.d3dkmt-standardallocation-existingheap, d3dkmthk/D3DKMT_STANDARDALLOCATION_EXISTINGHEAP
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3dkmthk.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : D3DKMT_STANDARDALLOCATION_EXISTINGHEAP
---

# _D3DKMT_STANDARDALLOCATION_EXISTINGHEAP structure
Holds information about the existing heap.

## Syntax
````
typedef struct _D3DKMT_STANDARDALLOCATION_EXISTINGHEAP {
  SIZE_T Size;
} D3DKMT_STANDARDALLOCATION_EXISTINGHEAP;
````

## Members


`Size`

Size in bytes of the existing heap.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dkmthk.h |
---
UID : NS:d3dkmddi._DXGK_QUERYGPUMMUCAPSIN
title : _DXGK_QUERYGPUMMUCAPSIN
author : windows-driver-content
description : The DXGK_QUERYGPUMMUCAPSIN structure holds the index of the adapter being queried.
old-location : display\dxgk_querygpummucapsin.htm
old-project : display
ms.assetid : 8DFD307F-DD4E-4321-AD97-78A5D67687B0
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _DXGK_QUERYGPUMMUCAPSIN, DXGK_QUERYGPUMMUCAPSIN
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3dkmddi.h
req.include-header : D3dkmddi.h
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : Windows Server 2016
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : DXGK_QUERYGPUMMUCAPSIN
req.alt-loc : d3dkmddi.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : DXGK_QUERYGPUMMUCAPSIN
---

# _DXGK_QUERYGPUMMUCAPSIN structure
The <b>DXGK_QUERYGPUMMUCAPSIN</b> structure holds the index of the adapter being queried.

## Syntax
````
typedef struct _DXGK_QUERYGPUMMUCAPSIN {
  UINT PhysicalAdapterIndex;
} DXGK_QUERYGPUMMUCAPSIN;
````

## Members

        
            `PhysicalAdapterIndex`

            A zero-based physical adapter index (engine ordinal) for which the data is queried.

    ## Remarks
        To get GpuMmu caps Dxgkrnl calls <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a> with the following parameters:</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |
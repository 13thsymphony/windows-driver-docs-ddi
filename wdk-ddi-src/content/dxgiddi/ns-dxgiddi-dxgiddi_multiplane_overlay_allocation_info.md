---
UID : NS:dxgiddi.DXGIDDI_MULTIPLANE_OVERLAY_ALLOCATION_INFO
title : DXGIDDI_MULTIPLANE_OVERLAY_ALLOCATION_INFO
author : windows-driver-content
description : Specifies info about a multiplane overlay allocation.
old-location : display\dxgiddi_multiplane_overlay_allocation_info.htm
old-project : display
ms.assetid : 2736b955-1b25-4ded-a75a-19a1c47f61ee
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : DXGIDDI_MULTIPLANE_OVERLAY_ALLOCATION_INFO, DXGIDDI_MULTIPLANE_OVERLAY_ALLOCATION_INFO
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : dxgiddi.h
req.include-header : D3d10umddi.h
req.target-type : Windows
req.target-min-winverclnt : Windows 8.1
req.target-min-winversvr : Windows Server 2012 R2
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : DXGIDDI_MULTIPLANE_OVERLAY_ALLOCATION_INFO
req.alt-loc : Dxgiddi.h
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
req.typenames : DXGIDDI_MULTIPLANE_OVERLAY_ALLOCATION_INFO
---

# DXGIDDI_MULTIPLANE_OVERLAY_ALLOCATION_INFO structure
Specifies info about a multiplane overlay allocation.

## Syntax
````
typedef struct DXGIDDI_MULTIPLANE_OVERLAY_ALLOCATION_INFO {
  D3DKMT_HANDLE PresentAllocation;
  UINT          SubResourceIndex;
} DXGIDDI_MULTIPLANE_OVERLAY_ALLOCATION_INFO;
````

## Members

        
            `PresentAllocation`

            [in] A handle to the multiplane overlay allocation.
        
            `SubResourceIndex`

            [in] The zero-based index into the resource which the handle in the <b>PresentAllocation</b> member specifies. This index indicates the display surface.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dxgiddi.h (include D3d10umddi.h) |
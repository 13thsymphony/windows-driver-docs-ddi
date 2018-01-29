---
UID : NS:d3dkmddi._DXGK_BUILDPAGINGBUFFER_FLUSHTLB
title : _DXGK_BUILDPAGINGBUFFER_FLUSHTLB
author : windows-driver-content
description : DXGK_BUILDPAGINGBUFFER_FLUSHTLB is used as part of a flush translation look-aside buffer (TLB) operation.
old-location : display\dxgk_buildpagingbuffer_flushtlb.htm
old-project : display
ms.assetid : 9FDE47A4-1784-41EB-9F60-76368D6DFEED
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : DXGK_BUILDPAGINGBUFFER_FLUSHTLB structure [Display Devices], d3dkmddi/DXGK_BUILDPAGINGBUFFER_FLUSHTLB, _DXGK_BUILDPAGINGBUFFER_FLUSHTLB, display.dxgk_buildpagingbuffer_flushtlb, DXGK_BUILDPAGINGBUFFER_FLUSHTLB
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : DXGK_BUILDPAGINGBUFFER_FLUSHTLB
---

# _DXGK_BUILDPAGINGBUFFER_FLUSHTLB structure
<b>DXGK_BUILDPAGINGBUFFER_FLUSHTLB</b> is used as part of a flush translation look-aside buffer (TLB) operation.

## Syntax
````
typedef struct _DXGK_BUILDPAGINGBUFFER_FLUSHTLB {
  D3DGPU_PHYSICAL_ADDRESS RootPageTableAddress;
  HANDLE                  hProcess;
  D3DGPU_PHYSICAL_ADDRESS StartVirtualAddress;
  D3DGPU_PHYSICAL_ADDRESS EndVirtualAddress;
} DXGK_BUILDPAGINGBUFFER_FLUSHTLB;
````

## Members


`EndVirtualAddress`

The end of the affected GPU virtual address range. When both <b>StartVirtualAddress</b> and <b>EndVirtualAddress</b> are zero, the entire GPU virtual address range is affected.

`hProcess`

KMD process handle,  returned from <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createprocess.md">DxgkDdiCreateProcess</a>, that the page table belongs to.

`RootPageTableAddress`

Physical address of the root page table being invalidated.

`StartVirtualAddress`

The start of the affected GPU virtual address range.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |
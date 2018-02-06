---
UID: NC:d3dkmddi.DXGKCB_MAPCONTEXTALLOCATION
title: DXGKCB_MAPCONTEXTALLOCATION
author: windows-driver-content
description: Maps a graphics processing unit (GPU) virtual address to the specified context allocation.
old-location: display\dxgkcbmapcontextallocation.htm
old-project: display
ms.assetid: 8EAC322D-B666-428A-99A3-96E489611832
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkcbmapcontextallocation, DxgkCbMapContextAllocation callback function [Display Devices], DxgkCbMapContextAllocation, DXGKCB_MAPCONTEXTALLOCATION, DXGKCB_MAPCONTEXTALLOCATION, d3dkmddi/DxgkCbMapContextAllocation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dkmddi.h
apiname:
-	DxgkCbMapContextAllocation
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKCB_MAPCONTEXTALLOCATION callback function
Maps a graphics processing unit (GPU) virtual address to the specified context allocation. This device driver interface (DDI) behaves like its user mode counterpart, see <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_mapgpuvirtualaddresscb.md">pfnMapGpuVirtualAddressCb</a> for more details.

## Syntax

```
DXGKCB_MAPCONTEXTALLOCATION DxgkcbMapcontextallocation;

D3DGPU_VIRTUAL_ADDRESS DxgkcbMapcontextallocation(
  IN_CONST_HANDLE hAdapter,
  IN_CONST_PDXGKARGCB_MAPCONTEXTALLOCATION pArgs
)
{...}
```

## Parameters

`hAdapter`

A handle to the display adapter.

`pArgs`

The <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkargcb_mapcontextallocation.md">DXGKARGCB_MAPCONTEXTALLOCATION</a> structure that describes the operation.


## Return Value

Returns a <b>D3DGPU_VIRTUAL_ADDRESS</b> if successful, <b>NULL</b> otherwise.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Target Platform** | Desktop |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkargcb_mapcontextallocation.md">DXGKARGCB_MAPCONTEXTALLOCATION</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_mapgpuvirtualaddresscb.md">pfnMapGpuVirtualAddressCb</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_MAPCONTEXTALLOCATION callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
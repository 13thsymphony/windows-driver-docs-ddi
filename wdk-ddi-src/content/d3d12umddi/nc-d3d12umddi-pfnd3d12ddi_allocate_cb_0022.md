---
UID: NC:d3d12umddi.PFND3D12DDI_ALLOCATE_CB_0022
title: PFND3D12DDI_ALLOCATE_CB_0022
author: windows-driver-content
description: The pfnAllocateCb callback function controls heap allocation by using a D3D12DDICB_ALLOCATE_0022 value.
old-location: display\pfnd3d12ddi_allocate_cb_0022.htm
old-project: display
ms.assetid: D0326C98-F187-4F62-AE60-60F0B38AB0D4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D12DDI_ALLOCATE_CB_0022, d3d12umddi/pfnAllocateCb, display.pfnd3d12ddi_allocate_cb_0022, pfnAllocateCb, pfnAllocateCb callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3d12umddi.h
api_name:
-	pfnAllocateCb
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---


# PFND3D12DDI_ALLOCATE_CB_0022 callback function
The <i>pfnAllocateCb</i> callback function controls heap allocation by using a <a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddicb_allocate_0022.md">D3D12DDICB_ALLOCATE_0022</a> value.

## Syntax

```
PFND3D12DDI_ALLOCATE_CB_0022 Pfnd3d12ddiAllocateCb0022;

HRESULT Pfnd3d12ddiAllocateCb0022(
   D3D12DDI_HRTDEVICE,
  D3D12DDICB_ALLOCATE_0022 *
)
{...}
```

## Parameters

`D3D12DDI_HRTDEVICE`



`*`




## Return Value

If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

## Remarks

Access this callback function by using the <a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_corelayer_devicecallbacks_0022.md">D3D12DDI_CORELAYER_DEVICECALLBACKS_0022</a> structure.

The driver must check the return value of the function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |

## See Also

<a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddicb_allocate_0022.md">D3D12DDICB_ALLOCATE_0022</a>



<a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_corelayer_devicecallbacks_0022.md">D3D12DDI_CORELAYER_DEVICECALLBACKS_0022</a>



<a href="..\d3d12umddi\nc-d3d12umddi-pfnd3d12ddi_deallocate_cb_0022.md">pfnDeallocateCb</a>
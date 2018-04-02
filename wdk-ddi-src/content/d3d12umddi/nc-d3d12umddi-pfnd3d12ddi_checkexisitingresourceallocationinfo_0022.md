---
UID: NC:d3d12umddi.PFND3D12DDI_CHECKEXISITINGRESOURCEALLOCATIONINFO_0022
title: PFND3D12DDI_CHECKEXISITINGRESOURCEALLOCATIONINFO_0022
author: windows-driver-content
description: The pfnCheckExistingResourceAllocationInfo callback function supports checking existing resource allocation information.
old-location: display\pfnd3d12ddi_checkexisitingresourceallocationinfo_0022.htm
old-project: display
ms.assetid: 428F23B4-3032-4BD9-A1C1-104BB2648F89
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3D12DDI_CHECKEXISITINGRESOURCEALLOCATIONINFO_0022, d3d12umddi/pfnCheckExistingResourceAllocationInfo, display.pfnd3d12ddi_checkexisitingresourceallocationinfo_0022, pfnCheckExistingResourceAllocationInfo, pfnCheckExistingResourceAllocationInfo callback function [Display Devices]
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
-	pfnCheckExistingResourceAllocationInfo
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---


# PFND3D12DDI_CHECKEXISITINGRESOURCEALLOCATIONINFO_0022 callback function
The <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt799844">pfnCheckExistingResourceAllocationInfo</a> callback function supports checking existing resource allocation information.

## Syntax

```
PFND3D12DDI_CHECKEXISITINGRESOURCEALLOCATIONINFO_0022 Pfnd3d12ddiCheckexisitingresourceallocationinfo0022;

void Pfnd3d12ddiCheckexisitingresourceallocationinfo0022(
   D3D12DDI_HDEVICE,
   D3D12DDI_HRESOURCE,
  D3D12DDI_RESOURCE_ALLOCATION_INFO_0022 *
)
{...}
```

## Parameters

`D3D12DDI_HDEVICE`



`D3D12DDI_HRESOURCE`



`*`




## Return Value

This callback function does not return a value.

## Remarks

This callback function is part of a two step process of resource creation. After the <a href="https://msdn.microsoft.com/9B223440-7462-4DF1-990B-82115DE50D67">pfnCheckResourceAllocationInfo</a> callback function, the resource is created. During resource creation, the layout is never _UNDEFINED, since the driver will have returned a resolved texture layout.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/9B223440-7462-4DF1-990B-82115DE50D67">pfnCheckResourceAllocationInfo</a>
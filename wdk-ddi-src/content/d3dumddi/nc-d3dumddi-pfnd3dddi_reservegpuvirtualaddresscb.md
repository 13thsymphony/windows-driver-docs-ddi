---
UID: NC:d3dumddi.PFND3DDDI_RESERVEGPUVIRTUALADDRESSCB
title: PFND3DDDI_RESERVEGPUVIRTUALADDRESSCB
author: windows-driver-content
description: pfnReserveGPUVirtualAddressCb reserves an address range in the current process graphics processing unit (GPU) virtual address space. The address range is only reserved, there is no actual memory behind it.
old-location: display\pfnreservegpuvirtualaddresscb.htm
old-project: display
ms.assetid: CEDE03E1-4B0D-4839-B7D6-0826CC103C5E
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3DDDI_RESERVEGPUVIRTUALADDRESSCB, d3dumddi/pfnReserveGpuVirtualAddressCb, display.pfnreservegpuvirtualaddresscb, pfnReserveGpuVirtualAddressCb, pfnReserveGpuVirtualAddressCb callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	pfnReserveGpuVirtualAddressCb
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_RESERVEGPUVIRTUALADDRESSCB callback function
<b>pfnReserveGPUVirtualAddressCb</b> reserves an address range in the current process graphics processing unit (GPU) virtual address space. The address range is only reserved, there is no actual memory behind it.


The user mode driver may choose the base GPU virtual address to use for the reservation by specifying a non-NULL value for <b>BaseAddress</b>. The video memory manager will use the specified range if it is available. If the range intersects with an existing range, the operation will fail. The user mode driver may pass a <b>NULL</b><b>BaseAddress</b> to let the video memory manager pick a base address.

When the user mode driver chooses to let the video memory manager pick a base address for the GPU virtual address range, it may choose to constrain the range that the video memory manager will consider by specifying non-NULL values for <b>MinimumAddress</b> and <b>MaximumAddress</b>. The video memory manager will ensure that the allocated GPU virtual address range is entirely contained in the range. The user mode driver may specify only a <b>MinimumAddress</b> (<b>MaximumAddress</b> being assumed to be the end of the address space) or only specify a <b>MaximumAddress</b> (<b>MinimumAddress</b> being assumed to be 0).

## Syntax

```
PFND3DDDI_RESERVEGPUVIRTUALADDRESSCB Pfnd3dddiReservegpuvirtualaddresscb;

HRESULT Pfnd3dddiReservegpuvirtualaddresscb(
  HANDLE hDevice,
  D3DDDI_RESERVEGPUVIRTUALADDRESS *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device.

`*`




## Return Value

If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dukmdt\ns-d3dukmdt-d3dddi_reservegpuvirtualaddress.md">D3DDDI_RESERVEGPUVIRTUALADDRESS</a>
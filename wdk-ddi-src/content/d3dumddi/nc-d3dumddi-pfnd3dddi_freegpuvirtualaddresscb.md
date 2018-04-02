---
UID: NC:d3dumddi.PFND3DDDI_FREEGPUVIRTUALADDRESSCB
title: PFND3DDDI_FREEGPUVIRTUALADDRESSCB
author: windows-driver-content
description: pfnFreeGpuVirtualAddressCb releases a range of graphics processing unit (GPU) virtual addresses that was previously reserved or mapped.
old-location: display\pfnfreegpuvirtualaddresscb.htm
old-project: display
ms.assetid: 92F2A43C-699B-4580-8A56-472D837A76E2
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3DDDI_FREEGPUVIRTUALADDRESSCB, d3dumddi/pfnFreeGpuVirtualAddressCb, display.pfnfreegpuvirtualaddresscb, pfnFreeGpuVirtualAddressCb, pfnFreeGpuVirtualAddressCb callback function [Display Devices]
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
-	pfnFreeGpuVirtualAddressCb
product:
- Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_FREEGPUVIRTUALADDRESSCB callback function
<b>pfnFreeGpuVirtualAddressCb</b> releases a range of graphics processing unit (GPU) virtual addresses that was previously reserved or mapped. 

The callback is a synchronous operation. The freed virtual address should not be accessed immediately after the call. If there are outstanding <a href="https://msdn.microsoft.com/DA67A98C-BE9C-412D-9382-CAC5B05FEE3B">pfnMapGpuVirtualAddressCb</a> and <a href="https://msdn.microsoft.com/99D075A0-4483-47D1-BA24-80C45BFF407A">pfnUpdateGpuVirtualAddressCb</a> operations, which reference the virtual address, they will be ignored after the virtual address is freed. A new virtual address range can be allocated in place of the freed one immediately after return from the function.

The user mode driver  must ensure that no allocation, which is used for current rendering operations, is mapped to the address range.


<div class="alert"><b>Note</b>  When an allocation is freed through <a href="https://msdn.microsoft.com/2ffa0367-0451-45d2-be05-e450c45be116">pfnDeallocateCb</a> all outstanding GPU virtual addresses are automatically released.</div>
<div> </div>

## Syntax

```
PFND3DDDI_FREEGPUVIRTUALADDRESSCB Pfnd3dddiFreegpuvirtualaddresscb;

HRESULT Pfnd3dddiFreegpuvirtualaddresscb(
  HANDLE hDevice,
  CONST D3DDDICB_FREEGPUVIRTUALADDRESS *
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

<a href="https://msdn.microsoft.com/library/windows/hardware/dn906763">D3DDDICB_FREEGPUVIRTUALADDRESS</a>



<a href="https://msdn.microsoft.com/2ffa0367-0451-45d2-be05-e450c45be116">pfnDeallocateCb</a>



<a href="https://msdn.microsoft.com/DA67A98C-BE9C-412D-9382-CAC5B05FEE3B">pfnMapGpuVirtualAddressCb</a>



<a href="https://msdn.microsoft.com/99D075A0-4483-47D1-BA24-80C45BFF407A">pfnUpdateGpuVirtualAddressCb</a>
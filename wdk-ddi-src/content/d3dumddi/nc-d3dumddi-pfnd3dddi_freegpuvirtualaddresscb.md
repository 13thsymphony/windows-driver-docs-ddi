---
UID: NC:d3dumddi.PFND3DDDI_FREEGPUVIRTUALADDRESSCB
title: PFND3DDDI_FREEGPUVIRTUALADDRESSCB
author: windows-driver-content
description: pfnFreeGpuVirtualAddressCb releases a range of graphics processing unit (GPU) virtual addresses that was previously reserved or mapped.
old-location: display\pfnfreegpuvirtualaddresscb.htm
old-project: display
ms.assetid: 92F2A43C-699B-4580-8A56-472D837A76E2
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.pfnfreegpuvirtualaddresscb, pfnFreeGpuVirtualAddressCb callback function [Display Devices], pfnFreeGpuVirtualAddressCb, PFND3DDDI_FREEGPUVIRTUALADDRESSCB, PFND3DDDI_FREEGPUVIRTUALADDRESSCB, d3dumddi/pfnFreeGpuVirtualAddressCb
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dumddi.h
apiname:
-	pfnFreeGpuVirtualAddressCb
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_FREEGPUVIRTUALADDRESSCB callback function
<b>pfnFreeGpuVirtualAddressCb</b> releases a range of graphics processing unit (GPU) virtual addresses that was previously reserved or mapped. 

The callback is a synchronous operation. The freed virtual address should not be accessed immediately after the call. If there are outstanding <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_mapgpuvirtualaddresscb.md">pfnMapGpuVirtualAddressCb</a> and <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_updategpuvirtualaddresscb.md">pfnUpdateGpuVirtualAddressCb</a> operations, which reference the virtual address, they will be ignored after the virtual address is freed. A new virtual address range can be allocated in place of the freed one immediately after return from the function.

The user mode driver  must ensure that no allocation, which is used for current rendering operations, is mapped to the address range.


<div class="alert"><b>Note</b>  When an allocation is freed through <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_deallocatecb.md">pfnDeallocateCb</a> all outstanding GPU virtual addresses are automatically released.</div>
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

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_updategpuvirtualaddresscb.md">pfnUpdateGpuVirtualAddressCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_mapgpuvirtualaddresscb.md">pfnMapGpuVirtualAddressCb</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_freegpuvirtualaddress.md">D3DDDICB_FREEGPUVIRTUALADDRESS</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_deallocatecb.md">pfnDeallocateCb</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_FREEGPUVIRTUALADDRESSCB callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
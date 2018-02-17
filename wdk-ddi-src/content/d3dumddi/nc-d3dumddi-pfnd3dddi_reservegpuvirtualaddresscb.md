---
UID: NC:d3dumddi.PFND3DDDI_RESERVEGPUVIRTUALADDRESSCB
title: PFND3DDDI_RESERVEGPUVIRTUALADDRESSCB
author: windows-driver-content
description: pfnReserveGPUVirtualAddressCb reserves an address range in the current process graphics processing unit (GPU) virtual address space. The address range is only reserved, there is no actual memory behind it.
old-location: display\pfnreservegpuvirtualaddresscb.htm
old-project: display
ms.assetid: CEDE03E1-4B0D-4839-B7D6-0826CC103C5E
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.pfnreservegpuvirtualaddresscb, pfnReserveGpuVirtualAddressCb callback function [Display Devices], pfnReserveGpuVirtualAddressCb, PFND3DDDI_RESERVEGPUVIRTUALADDRESSCB, PFND3DDDI_RESERVEGPUVIRTUALADDRESSCB, d3dumddi/pfnReserveGpuVirtualAddressCb
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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_RESERVEGPUVIRTUALADDRESSCB callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
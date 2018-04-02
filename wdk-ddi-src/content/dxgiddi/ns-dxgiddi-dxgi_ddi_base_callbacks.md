---
UID: NS:dxgiddi.DXGI_DDI_BASE_CALLBACKS
title: DXGI_DDI_BASE_CALLBACKS
author: windows-driver-content
description: The DXGI_DDI_BASE_CALLBACKS structure contains pointers to Microsoft Direct3D 10 runtime callback functions that the user-mode display driver can use.
old-location: display\dxgi_ddi_base_callbacks.htm
old-project: display
ms.assetid: dd1690e2-7eef-4086-a3e1-9ca456b79a6f
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGI_DDI_BASE_CALLBACKS, DXGI_DDI_BASE_CALLBACKS structure [Display Devices], UMDisplayDriver_Dx10param_Structs_6622df62-429f-438b-aa1a-61fd7fb8df65.xml, display.dxgi_ddi_base_callbacks, dxgiddi/DXGI_DDI_BASE_CALLBACKS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	HeaderDef
api_location:
-	dxgiddi.h
api_name:
-	DXGI_DDI_BASE_CALLBACKS
product:
- Windows
targetos: Windows
req.typenames: DXGI_DDI_BASE_CALLBACKS
---

# DXGI_DDI_BASE_CALLBACKS structure
The DXGI_DDI_BASE_CALLBACKS structure contains pointers to Microsoft Direct3D 10 runtime callback functions that the user-mode display driver can use.

## Syntax
```
typedef struct DXGI_DDI_BASE_CALLBACKS {
  PFNDDXGIDDI_PRESENTCB                     pfnPresentCb;
  PFNDDXGIDDI_PRESENT_MULTIPLANE_OVERLAYCB  pfnPresentMultiplaneOverlayCb;
  PFNDDXGIDDI_PRESENT_MULTIPLANE_OVERLAY1CB pfnPresentMultiplaneOverlay1Cb;
};
```

## Members


`pfnPresentCb`

A pointer to the <a href="https://msdn.microsoft.com/eefb8f2c-e460-4f9c-851d-9a97dbcd728f">pfnPresentCbDXGI</a> function.

`pfnPresentMultiplaneOverlayCb`

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh780324">pfnPresentMultiPlaneOverlayCb (DXGI)</a> function. Supported starting with Windows 8.1.

`pfnPresentMultiplaneOverlay1Cb`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | dxgiddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541664">D3D10DDIARG_CREATEDEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557485">DXGI_DDI_BASE_ARGS</a>



<a href="https://msdn.microsoft.com/eefb8f2c-e460-4f9c-851d-9a97dbcd728f">pfnPresentCbDXGI</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh780324">pfnPresentMultiPlaneOverlayCb (DXGI)</a>
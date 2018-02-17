---
UID: NS:dxgiddi.DXGI_DDI_BASE_CALLBACKS
title: DXGI_DDI_BASE_CALLBACKS
author: windows-driver-content
description: The DXGI_DDI_BASE_CALLBACKS structure contains pointers to Microsoft Direct3D 10 runtime callback functions that the user-mode display driver can use.
old-location: display\dxgi_ddi_base_callbacks.htm
old-project: display
ms.assetid: dd1690e2-7eef-4086-a3e1-9ca456b79a6f
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgi_ddi_base_callbacks, DXGI_DDI_BASE_CALLBACKS, dxgiddi/DXGI_DDI_BASE_CALLBACKS, DXGI_DDI_BASE_CALLBACKS structure [Display Devices], UMDisplayDriver_Dx10param_Structs_6622df62-429f-438b-aa1a-61fd7fb8df65.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	dxgiddi.h
apiname:
-	DXGI_DDI_BASE_CALLBACKS
product: Windows
targetos: Windows
req.typenames: DXGI_DDI_BASE_CALLBACKS
---

# DXGI_DDI_BASE_CALLBACKS structure
The DXGI_DDI_BASE_CALLBACKS structure contains pointers to Microsoft Direct3D 10 runtime callback functions that the user-mode display driver can use.

## Syntax
````
typedef struct DXGI_DDI_BASE_CALLBACKS {
  PFNDDXGIDDI_PRESENTCB                    pfnPresentCb;
#if (D3D_UMD_INTERFACE_VERSION >= D3D_UMD_INTERFACE_VERSION_WIN8)
  PFNDDXGIDDI_PRESENT_MULTIPLANE_OVERLAYCB pfnPresentMultiplaneOverlayCb;
#endif 
} DXGI_DDI_BASE_CALLBACKS;
````

## Members


`pfnPresentCb`

A pointer to the <a href="..\dxgiddi\nc-dxgiddi-pfnddxgiddi_presentcb.md">pfnPresentCbDXGI</a> function.

`pfnPresentMultiplaneOverlay1Cb`



`pfnPresentMultiplaneOverlayCb`

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh780324">pfnPresentMultiPlaneOverlayCb (DXGI)</a> function. Supported starting with Windows 8.1.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | dxgiddi.h (include D3d10umddi.h) |

## See Also

<a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_base_args.md">DXGI_DDI_BASE_ARGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh780324">pfnPresentMultiPlaneOverlayCb (DXGI)</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createdevice.md">D3D10DDIARG_CREATEDEVICE</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>



<a href="..\dxgiddi\nc-dxgiddi-pfnddxgiddi_presentcb.md">pfnPresentCbDXGI</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGI_DDI_BASE_CALLBACKS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
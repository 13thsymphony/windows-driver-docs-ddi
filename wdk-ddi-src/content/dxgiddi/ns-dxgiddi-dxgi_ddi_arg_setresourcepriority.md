---
UID: NS:dxgiddi.DXGI_DDI_ARG_SETRESOURCEPRIORITY
title: DXGI_DDI_ARG_SETRESOURCEPRIORITY
author: windows-driver-content
description: The DXGI_DDI_ARG_SETRESOURCEPRIORITY structure describes parameters for setting the priority level of a resource.
old-location: display\dxgi_ddi_arg_setresourcepriority.htm
old-project: display
ms.assetid: 9d3f5687-bc49-4831-bf56-5d4201ed45de
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGI_DDI_ARG_SETRESOURCEPRIORITY, DXGI_DDI_ARG_SETRESOURCEPRIORITY structure [Display Devices], UMDisplayDriver_Dx10param_Structs_fda8895f-9cc7-496b-ae2e-bf6b076fc0b3.xml, display.dxgi_ddi_arg_setresourcepriority, dxgiddi/DXGI_DDI_ARG_SETRESOURCEPRIORITY
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
-	DXGI_DDI_ARG_SETRESOURCEPRIORITY
product: Windows
targetos: Windows
req.typenames: DXGI_DDI_ARG_SETRESOURCEPRIORITY
---

# DXGI_DDI_ARG_SETRESOURCEPRIORITY structure
The DXGI_DDI_ARG_SETRESOURCEPRIORITY structure describes parameters for setting the priority level of a resource.

## Syntax
````
typedef struct DXGI_DDI_ARG_SETRESOURCEPRIORITY {
  DXGI_DDI_HDEVICE   hDevice;
  DXGI_DDI_HRESOURCE hResource;
  UINT               Priority;
} DXGI_DDI_ARG_SETRESOURCEPRIORITY;
````

## Members


`hDevice`

[in] A handle to the display device (graphics context) on which the driver sets the eviction-from-memory priority for a resource. The Direct3D runtime passes this handle to the driver in the <b>hDrvDevice</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createdevice.md">D3D10DDIARG_CREATEDEVICE</a> structure when the runtime calls the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a> function to create the display device.

`hResource`

[in] A handle to the resource to set the priority level for.

`Priority`

[in] The priority level to set for the resource that the <b>hResource</b> member specifies. A resource's priority level can be set anywhere in the range from 0 through 0xFFFFFFFF.

## Remarks
The priority level that a resource is set at determines its eviction order from memory. A resource that is assigned a low priority is evicted before a resource with a high priority. If two resources have the same priority, the resource that was used more recently is kept in memory; the other resource is evicted.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | dxgiddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569657">SetResourcePriorityDXGI</a>
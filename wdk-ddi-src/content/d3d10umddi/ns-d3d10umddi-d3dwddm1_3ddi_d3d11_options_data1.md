---
UID: NS:d3d10umddi.D3DWDDM1_3DDI_D3D11_OPTIONS_DATA1
title: D3DWDDM1_3DDI_D3D11_OPTIONS_DATA1
author: windows-driver-content
description: Specifies the level of support by the hardware and user-mode display driver for tiled resources.
old-location: display\d3dwddm1_3ddi_d3d11_options_data1.htm
old-project: display
ms.assetid: 822819CE-DF40-4AFD-966A-DA5C433646D7
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DWDDM1_3DDI_D3D11_OPTIONS_DATA1, D3DWDDM1_3DDI_D3D11_OPTIONS_DATA1 structure [Display Devices], d3d10umddi/D3DWDDM1_3DDI_D3D11_OPTIONS_DATA1, display.d3dwddm1_3ddi_d3d11_options_data1
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1,WDDM 1.3 and later
req.target-min-winversvr: Windows Server 2012 R2
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
-	d3d10umddi.h
api_name:
-	D3DWDDM1_3DDI_D3D11_OPTIONS_DATA1
product: Windows
targetos: Windows
req.typenames: D3DWDDM1_3DDI_D3D11_OPTIONS_DATA1
---

# D3DWDDM1_3DDI_D3D11_OPTIONS_DATA1 structure
Specifies the level of support by the hardware and user-mode display driver for tiled resources.

## Syntax
```
typedef struct D3DWDDM1_3DDI_D3D11_OPTIONS_DATA1 {
  UINT TiledResourcesSupportFlags;
};
```

## Members


`TiledResourcesSupportFlags`

A value from the <a href="https://msdn.microsoft.com/library/windows/hardware/dn475745">D3DWDDM1_3DDI_TILED_RESOURCES_SUPPORT_FLAG</a> enumeration that indicates the level of support  for tiled resources.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1,WDDM 1.3 and later Windows 8.1,WDDM 1.3 and later |
| **Header** | d3d10umddi.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn475745">D3DWDDM1_3DDI_TILED_RESOURCES_SUPPORT_FLAG</a>
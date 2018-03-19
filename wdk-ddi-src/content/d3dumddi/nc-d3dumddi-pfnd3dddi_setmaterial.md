---
UID: NC:d3dumddi.PFND3DDDI_SETMATERIAL
title: PFND3DDDI_SETMATERIAL
author: windows-driver-content
description: The SetMaterial function sets the material properties that devices on the system use to create the required effect during rendering.
old-location: display\setmaterial.htm
old-project: display
ms.assetid: e1273478-a450-44fa-95d5-ee86cb3a46b2
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3DDDI_SETMATERIAL, SetMaterial, SetMaterial callback function [Display Devices], UserModeDisplayDriver_Functions_004e812d-4be5-4222-9a29-e206e17a2fa1.xml, d3dumddi/SetMaterial, display.setmaterial
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
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
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	SetMaterial
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_SETMATERIAL callback function
The <i>SetMaterial</i> function sets the material properties that devices on the system use to create the required effect during rendering.

## Syntax

```
PFND3DDDI_SETMATERIAL Pfnd3dddiSetmaterial;

HRESULT Pfnd3dddiSetmaterial(
  HANDLE hDevice,
  CONST D3DDDIARG_SETMATERIAL *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`




## Return Value

<i>SetMaterial</i> returns S_OK or an appropriate error result if the material properties are not successfully set.

## Remarks

Material properties detail a material's diffuse reflection, ambient reflection, light emission, and specular highlighting characteristics. The Microsoft Direct3D runtime uses the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_setmaterial.md">D3DDDIARG_SETMATERIAL</a> structure to pass all of the material property information to the user-mode display driver. Material properties affect the colors that the Direct3D runtime uses to rasterize polygons that use the material. With the exception of the specular property, each of the properties is described as an RGBA color that represents how much of the red, green, and blue parts of a given type of light it reflects and an alpha blending factor (the alpha component of the RGBA color). The material's specular property is described in two parts: color and power. For more information about material properties, see the Microsoft Windows SDK documentation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_setmaterial.md">D3DDDIARG_SETMATERIAL</a>
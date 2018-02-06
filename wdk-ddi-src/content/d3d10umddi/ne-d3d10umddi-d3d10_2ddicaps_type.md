---
UID: NE:d3d10umddi.D3D10_2DDICAPS_TYPE
title: D3D10_2DDICAPS_TYPE
author: windows-driver-content
description: The D3D10_2DDICAPS_TYPE enumeration type contains values that identify the type of capability information that is retrieved from a call to the driver's GetCaps(D3D10_2) function.
old-location: display\d3d10_2ddicaps_type.htm
old-project: display
ms.assetid: 2ca906d4-6d09-4624-a985-a47794acc959
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3d10umddi/D3DWDDM1_3DDICAPS_MARKER, D3DWDDM1_3DDICAPS_D3D11_OPTIONS1, d3d10umddi/D3D11_1DDICAPS_SHADER_MIN_PRECISION_SUPPORT, display.d3d10_2ddicaps_type, D3D11DDICAPS_THREADING, d3d10umddi/D3D11DDICAPS_SHADER, d3d10umddi/D3D10_2DDICAPS_TYPE, D3D11_1DDICAPS_D3D11_OPTIONS, d3d10umddi/D3D11DDICAPS_THREADING, UMDisplayDriver_Dx11param_Structs_cde2c336-2e65-43c4-970c-83b83765df38.xml, D3DWDDM1_3DDICAPS_MARKER, d3d10umddi/D3D11_1DDICAPS_ARCHITECTURE_INFO, D3D11DDICAPS_SHADER, D3D10_2DDICAPS_TYPE enumeration [Display Devices], d3d10umddi/D3D11DDICAPS_3DPIPELINESUPPORT, d3d10umddi/D3DWDDM1_3DDICAPS_D3D11_OPTIONS1, D3D11DDICAPS_3DPIPELINESUPPORT, D3D11_1DDICAPS_ARCHITECTURE_INFO, D3D11_1DDICAPS_SHADER_MIN_PRECISION_SUPPORT, d3d10umddi/D3D11_1DDICAPS_D3D11_OPTIONS, D3D10_2DDICAPS_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D10_2DDICAPS_TYPE is supported beginning with the Windows 7 operating system.
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
-	d3d10umddi.h
apiname:
-	D3D10_2DDICAPS_TYPE
product: Windows
targetos: Windows
req.typenames: D3D10_2DDICAPS_TYPE
---

# D3D10_2DDICAPS_TYPE Enumeration
The D3D10_2DDICAPS_TYPE enumeration type contains values that identify the type of capability information that is retrieved from a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_2ddi_getcaps.md">GetCaps(D3D10_2)</a> function.

## Syntax
````
enum D3D10_2DDICAPS_TYPE {
  D3D11DDICAPS_THREADING                       = 128, 
  D3D11DDICAPS_SHADER                          = 129, 
  D3D11DDICAPS_3DPIPELINESUPPORT               = 130, 
#if D3D11DDI_MINOR_HEADER_VERSION >= 3
  D3D11_1DDICAPS_D3D11_OPTIONS                 = 131, 
  D3D11_1DDICAPS_ARCHITECTURE_INFO             = 132, 
  D3D11_1DDICAPS_SHADER_MIN_PRECISION_SUPPORT  = 134, 
#endif 
#if D3D11DDI_MINOR_HEADER_VERSION >= 4
  D3DWDDM1_3DDICAPS_D3D11_OPTIONS1             = 136, 
  D3DWDDM1_3DDICAPS_MARKER                     = 137 

#endif 
};
````

## Constants

<table>
            
                <tr>
                    <td>D3D11_1DDICAPS_ARCHITECTURE_INFO</td>
                    <td>The driver retrieves a pointer to a <a href="..\d3dumddi\ns-d3dumddi-d3dddicaps_architecture_info.md">D3DDDICAPS_ARCHITECTURE_INFO</a> structure that describes information about Direct3D 11.1 adapter architecture.

Supported starting with Windows 8.</td>
                </tr>
            
                <tr>
                    <td>D3D11_1DDICAPS_D3D11_OPTIONS</td>
                    <td>The driver retrieves a pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_d3d11_options_data.md">D3D11_1DDI_D3D11_OPTIONS_DATA</a>  structure that specifies options to provide data to the user-mode driver.

Supported starting with Windows 8.</td>
                </tr>
            
                <tr>
                    <td>D3D11_1DDICAPS_SHADER_MIN_PRECISION_SUPPORT</td>
                    <td>The driver retrieves a pointer to a <a href="..\d3dumddi\ns-d3dumddi-d3dddicaps_shader_min_precision_support.md">D3DDDICAPS_SHADER_MIN_PRECISION_SUPPORT</a> structure that describes the precision support options for shaders in the user-mode display driver.

Supported starting with Windows 8.</td>
                </tr>
            
                <tr>
                    <td>D3D11DDICAPS_3DPIPELINESUPPORT</td>
                    <td>The driver retrieves a pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_3dpipelinesupport_caps.md">D3D11DDI_3DPIPELINESUPPORT_CAPS</a> structure that describes the pipeline capabilities that the driver supports.</td>
                </tr>
            
                <tr>
                    <td>D3D11DDICAPS_SHADER</td>
                    <td>The driver retrieves a pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_shader_caps.md">D3D11DDI_SHADER_CAPS</a> structure that describes the shader capabilities that the driver supports.</td>
                </tr>
            
                <tr>
                    <td>D3D11DDICAPS_THREADING</td>
                    <td>The driver retrieves a pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_threading_caps.md">D3D11DDI_THREADING_CAPS</a> structure that describes the threading capabilities that the driver supports.</td>
                </tr>
            
                <tr>
                    <td>D3DWDDM1_3DDICAPS_D3D11_OPTIONS1</td>
                    <td>The driver retrieves a pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm1_3ddi_d3d11_options_data1.md">D3DWDDM1_3DDI_D3D11_OPTIONS_DATA1</a> structure that describes the tiled resource support options in the user-mode display driver.

Supported starting with Windows 8. Used by WDDM 1.3 and later drivers.</td>
                </tr>
            
                <tr>
                    <td>D3DWDDM1_3DDICAPS_MARKER</td>
                    <td>Supported starting with Windows 8. Used by WDDM 1.3 and later drivers.</td>
                </tr>
            
                <tr>
                    <td>D3DWDDM2_0DDICAPS_D3D11_OPTIONS2</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>D3DWDDM2_0DDICAPS_D3D11_OPTIONS3</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>D3DWDDM2_0DDICAPS_GPUVA_CAPS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>D3DWDDM2_0DDICAPS_MEMORY_ARCHITECTURE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>D3DWDDM2_0DDICAPS_SWIZZLE_PATTERN</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>D3DWDDM2_0DDICAPS_TEXTURE_LAYOUT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>D3DWDDM2_0DDICAPS_TEXTURE_LAYOUT_SETS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>D3DWDDM2_0DDICAPS_TEXTURE_LAYOUT1</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>D3DWDDM2_2DDICAPS_SHADERCACHE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>D3DWDDM2_2DDICAPS_SWIZZLE_PATTERN</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>D3DWDDM2_2DDICAPS_TEXTURE_LAYOUT</td>
                    <td></td>
                </tr>
</table>

    ## Remarks

        To allow a driver to unify capability concepts, the values in the D3D10_2DDICAPS_TYPE enumeration are set up so they do not overlap with the values in the <a href="..\d3dumddi\ne-d3dumddi-_d3dddicaps_type.md">D3DDDICAPS_TYPE</a> enumeration.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | D3D10_2DDICAPS_TYPE is supported beginning with the Windows 7 operating system. D3D10_2DDICAPS_TYPE is supported beginning with the Windows 7 operating system. |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

    ## See Also

        <a href="..\d3dumddi\ne-d3dumddi-_d3dddicaps_type.md">D3DDDICAPS_TYPE</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_d3d11_options_data.md">D3D11_1DDI_D3D11_OPTIONS_DATA</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_shader_caps.md">D3D11DDI_SHADER_CAPS</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_threading_caps.md">D3D11DDI_THREADING_CAPS</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm1_3ddi_d3d11_options_data1.md">D3DWDDM1_3DDI_D3D11_OPTIONS_DATA1</a>

<a href="..\d3dumddi\ns-d3dumddi-d3dddicaps_shader_min_precision_support.md">D3DDDICAPS_SHADER_MIN_PRECISION_SUPPORT</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_3dpipelinesupport_caps.md">D3D11DDI_3DPIPELINESUPPORT_CAPS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10_2DDICAPS_TYPE enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
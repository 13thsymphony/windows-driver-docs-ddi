---
UID: NE:d3dukmdt._D3DDDI_GAMMARAMP_TYPE
title: "_D3DDDI_GAMMARAMP_TYPE"
author: windows-driver-content
description: The D3DDDI_GAMMARAMP_TYPE enumeration indicates the type of gamma ramp used in a video present path.
old-location: display\d3dddi_gammaramp_type.htm
old-project: display
ms.assetid: 4261989f-5f29-4957-9633-ce2de14698fa
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDI_GAMMARAMP_DEFAULT, D3DDDI_GAMMARAMP_DXGI_1, D3DDDI_GAMMARAMP_MATRIX_3x4, D3DDDI_GAMMARAMP_RGB256x3x16, D3DDDI_GAMMARAMP_TYPE, D3DDDI_GAMMARAMP_TYPE enumeration [Display Devices], D3DDDI_GAMMARAMP_UNINITIALIZED, DmEnums_fc19c762-0156-4602-97ea-0b3865012161.xml, _D3DDDI_GAMMARAMP_TYPE, d3dukmdt/D3DDDI_GAMMARAMP_DEFAULT, d3dukmdt/D3DDDI_GAMMARAMP_DXGI_1, d3dukmdt/D3DDDI_GAMMARAMP_MATRIX_3x4, d3dukmdt/D3DDDI_GAMMARAMP_RGB256x3x16, d3dukmdt/D3DDDI_GAMMARAMP_TYPE, d3dukmdt/D3DDDI_GAMMARAMP_UNINITIALIZED, display.d3dddi_gammaramp_type
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dukmdt.h
req.include-header: D3dukmdt.h
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
-	d3dukmdt.h
api_name:
-	D3DDDI_GAMMARAMP_TYPE
product: Windows
targetos: Windows
req.typenames: D3DDDI_GAMMARAMP_TYPE
---

# _D3DDDI_GAMMARAMP_TYPE Enumeration
The D3DDDI_GAMMARAMP_TYPE enumeration indicates the type of gamma ramp used in a video present path.

## Syntax
````
typedef enum _D3DDDI_GAMMARAMP_TYPE { 
  D3DDDI_GAMMARAMP_UNINITIALIZED  = 0,
  D3DDDI_GAMMARAMP_DEFAULT        = 1,
  D3DDDI_GAMMARAMP_RGB256x3x16    = 2,
  D3DDDI_GAMMARAMP_DXGI_1         = 3,
#if DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_3
  D3DDDI_GAMMARAMP_MATRIX_3x4     = 4

#endif } D3DDDI_GAMMARAMP_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>D3DDDI_GAMMARAMP_DEFAULT</td>
                    <td>Indicates the default gamma ramp.</td>
                </tr>
            
                <tr>
                    <td>D3DDDI_GAMMARAMP_DXGI_1</td>
                    <td>Indicates that the gamma lookup table is described by a <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_gamma_ramp_dxgi_1.md">D3DDDI_GAMMA_RAMP_DXGI_1</a> structure.</td>
                </tr>
            
                <tr>
                    <td>D3DDDI_GAMMARAMP_MATRIX_3x4</td>
                    <td>Indicates that the colorspace transform is defined by a D3DDDI_3X4_COLORSPACE_TRANSFORM structure.</td>
                </tr>
            
                <tr>
                    <td>D3DDDI_GAMMARAMP_RGB256x3x16</td>
                    <td>Indicates that the gamma lookup table contains three arrays, one each for the red, green, and blue color channels. Each array has 256 16-bit values.</td>
                </tr>
            
                <tr>
                    <td>D3DDDI_GAMMARAMP_UNINITIALIZED</td>
                    <td>Indicates that a variable of type D3DDDI_GAMMARAMP_TYPE has not yet been assigned a meaningful value.</td>
                </tr>
</table>

## Remarks

The <b>GammaRamp</b> member of the <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_present_path.md">D3DKMDT_VIDPN_PRESENT_PATH</a> structure is a <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_gamma_ramp.md">D3DKMDT_GAMMA_RAMP</a> structure. The <b>Type</b> member of the D3DKMDT_GAMMA_RAMP structure is a D3DDDI_GAMMARAMP_TYPE value.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dukmdt.h (include D3dukmdt.h) |

## See Also

<a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_color_basis.md">D3DKMDT_COLOR_BASIS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_GAMMARAMP_TYPE enumeration%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
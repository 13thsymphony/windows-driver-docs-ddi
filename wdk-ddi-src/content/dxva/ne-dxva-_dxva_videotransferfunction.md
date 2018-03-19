---
UID: NE:dxva._DXVA_VideoTransferFunction
title: "_DXVA_VideoTransferFunction"
author: windows-driver-content
description: The DXVA_VideoTransferFunction enumeration type contains enumerators that identify the conversion function from R'G'B' to RGB.
old-location: display\dxva_videotransferfunction.htm
old-project: display
ms.assetid: 2ed04fd0-685d-4b5a-a23f-337a14506f8b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXVA_VideoTransFuncMask, DXVA_VideoTransFuncShift, DXVA_VideoTransFunc_10, DXVA_VideoTransFunc_18, DXVA_VideoTransFunc_20, DXVA_VideoTransFunc_22, DXVA_VideoTransFunc_22_240M, DXVA_VideoTransFunc_22_709, DXVA_VideoTransFunc_22_8bit_sRGB, DXVA_VideoTransFunc_28, DXVA_VideoTransFunc_Unknown, DXVA_VideoTransferFunction, DXVA_VideoTransferFunction enumeration [Display Devices], _DXVA_VideoTransferFunction, display.dxva_videotransferfunction, dxva/DXVA_VideoTransFuncMask, dxva/DXVA_VideoTransFuncShift, dxva/DXVA_VideoTransFunc_10, dxva/DXVA_VideoTransFunc_18, dxva/DXVA_VideoTransFunc_20, dxva/DXVA_VideoTransFunc_22, dxva/DXVA_VideoTransFunc_22_240M, dxva/DXVA_VideoTransFunc_22_709, dxva/DXVA_VideoTransFunc_22_8bit_sRGB, dxva/DXVA_VideoTransFunc_28, dxva/DXVA_VideoTransFunc_Unknown, dxva/DXVA_VideoTransferFunction, dxvaref_67be6e0a-79c6-4821-b3c3-899c2a2f9234.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: This enumeration type applies only to Windows Server 2003 with SP1 and later, and Windows XP with SP2 and later.
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
-	dxva.h
api_name:
-	DXVA_VideoTransferFunction
product: Windows
targetos: Windows
req.typenames: DXVA_VideoTransferFunction
---

# _DXVA_VideoTransferFunction Enumeration
The DXVA_VideoTransferFunction enumeration type contains enumerators that identify the conversion function from R'G'B' to RGB.

## Syntax
````
typedef enum _DXVA_VideoTransferFunction { 
  DXVA_VideoTransFuncShift          = (DXVA_ExtColorData_ShiftBase + 19),
  DXVA_VideoTransFuncMask           = DXVAColorMask(5, DXVA_VideoTransFuncShift),
  DXVA_VideoTransFunc_Unknown       = 0,
  DXVA_VideoTransFunc_10            = 1,
  DXVA_VideoTransFunc_18            = 2,
  DXVA_VideoTransFunc_20            = 3,
  DXVA_VideoTransFunc_22            = 4,
  DXVA_VideoTransFunc_22_709        = 5,
  DXVA_VideoTransFunc_22_240M       = 6,
  DXVA_VideoTransFunc_22_8bit_sRGB  = 7,
  DXVA_VideoTransFunc_28            = 8
} DXVA_VideoTransferFunction;
````

## Constants

<table>
            
                <tr>
                    <td>DXVA_VideoTransFuncShift</td>
                    <td>Specifies to shift bits by 27 positions (DXVA_ExtColorData_ShiftBase + 19, or 8 + 19).</td>
                </tr>
            
                <tr>
                    <td>DXVA_VideoTransFuncMask</td>
                    <td>Specifies the video transfer function mask. 5 (0xF8000000) bits of a DWORD can be used to specify the video transfer function.</td>
                </tr>
            
                <tr>
                    <td>DXVA_VideoTransFunc_Unknown</td>
                    <td>Specifies that the video transfer function is not specified. The default is 22_8bit_sRGB if required for a computation.</td>
                </tr>
            
                <tr>
                    <td>DXVA_VideoTransFunc_10</td>
                    <td>Specifies linear RGB conversion (corresponds to gamma = 1.0).</td>
                </tr>
            
                <tr>
                    <td>DXVA_VideoTransFunc_18</td>
                    <td>Specifies true 1.8 gamma. That is, L' = pow(L, 1/gamma) for L=0..1.</td>
                </tr>
            
                <tr>
                    <td>DXVA_VideoTransFunc_20</td>
                    <td>Specifies true 2.0 gamma. That is, L' = pow(L, 1/gamma) for L=0..1.</td>
                </tr>
            
                <tr>
                    <td>DXVA_VideoTransFunc_22</td>
                    <td>######### 



######</td>
                </tr>
            
                <tr>
                    <td>DXVA_VideoTransFunc_22_709</td>
                    <td>###### 



#####</td>
                </tr>
            
                <tr>
                    <td>DXVA_VideoTransFunc_22_240M</td>
                    <td>###### 



#####</td>
                </tr>
            
                <tr>
                    <td>DXVA_VideoTransFunc_22_8bit_sRGB</td>
                    <td>Specifies gamma 2.4 curve with a linear range in the low range, which makes it match an accurate 2.2 gamma 8 bit curve.</td>
                </tr>
            
                <tr>
                    <td>DXVA_VideoTransFunc_28</td>
                    <td>Specifies true 2.8 gamma. That is, L' = pow(L, 1/gamma) for L=0..1.</td>
                </tr>
</table>

## Remarks

One of the enumerators of DXVA_VideoTransferFunction can be specified in the <b>VideoTransferFunction</b> member of the <a href="..\dxva\ns-dxva-_dxva_extendedformat.md">DXVA_ExtendedFormat</a> structure.

DXVA_VideoTransferFunction corresponds to the gamma function of the data. Some transfer functions have corrections to account for 8 bit integer quantization effects.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | This enumeration type applies only to Windows Server 2003 with SP1 and later, and Windows XP with SP2 and later. This enumeration type applies only to Windows Server 2003 with SP1 and later, and Windows XP with SP2 and later. |
| **Header** | dxva.h (include Dxva.h) |

## See Also

<a href="..\dxva\ns-dxva-_dxva_extendedformat.md">DXVA_ExtendedFormat</a>
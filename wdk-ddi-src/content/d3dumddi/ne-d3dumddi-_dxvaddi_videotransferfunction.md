---
UID: NE:d3dumddi._DXVADDI_VIDEOTRANSFERFUNCTION
title: "_DXVADDI_VIDEOTRANSFERFUNCTION"
author: windows-driver-content
description: The DXVADDI_VIDEOTRANSFERFUNCTION enumeration type contains values that identify the conversion function from R'G'B' to RGB.
old-location: display\dxvaddi_videotransferfunction.htm
old-project: display
ms.assetid: 8d798afe-dc75-4cd0-aad7-1f9824bdcf00
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXVA2_Structs_a6fcb795-da10-4824-99b3-5f75a50a17ce.xml, DXVADDI_VIDEOTRANSFERFUNCTION, DXVADDI_VIDEOTRANSFERFUNCTION enumeration [Display Devices], DXVADDI_VideoTransFuncMask, DXVADDI_VideoTransFunc_10, DXVADDI_VideoTransFunc_18, DXVADDI_VideoTransFunc_20, DXVADDI_VideoTransFunc_22, DXVADDI_VideoTransFunc_240M, DXVADDI_VideoTransFunc_28, DXVADDI_VideoTransFunc_709, DXVADDI_VideoTransFunc_Unknown, DXVADDI_VideoTransFunc_sRGB, _DXVADDI_VIDEOTRANSFERFUNCTION, d3dumddi/DXVADDI_VIDEOTRANSFERFUNCTION, d3dumddi/DXVADDI_VideoTransFuncMask, d3dumddi/DXVADDI_VideoTransFunc_10, d3dumddi/DXVADDI_VideoTransFunc_18, d3dumddi/DXVADDI_VideoTransFunc_20, d3dumddi/DXVADDI_VideoTransFunc_22, d3dumddi/DXVADDI_VideoTransFunc_240M, d3dumddi/DXVADDI_VideoTransFunc_28, d3dumddi/DXVADDI_VideoTransFunc_709, d3dumddi/DXVADDI_VideoTransFunc_Unknown, d3dumddi/DXVADDI_VideoTransFunc_sRGB, display.dxvaddi_videotransferfunction
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	d3dumddi.h
api_name:
-	DXVADDI_VIDEOTRANSFERFUNCTION
product:
- Windows
targetos: Windows
req.typenames: DXVADDI_VIDEOTRANSFERFUNCTION
---

# _DXVADDI_VIDEOTRANSFERFUNCTION Enumeration
The DXVADDI_VIDEOTRANSFERFUNCTION enumeration type contains values that identify the conversion function from R'G'B' to RGB.

## Syntax
```
typedef enum _DXVADDI_VIDEOTRANSFERFUNCTION {
  DXVADDI_VideoTransFuncMask      ,
  DXVADDI_VideoTransFunc_Unknown  ,
  DXVADDI_VideoTransFunc_10       ,
  DXVADDI_VideoTransFunc_18       ,
  DXVADDI_VideoTransFunc_20       ,
  DXVADDI_VideoTransFunc_22       ,
  DXVADDI_VideoTransFunc_709      ,
  DXVADDI_VideoTransFunc_240M     ,
  DXVADDI_VideoTransFunc_sRGB     ,
  DXVADDI_VideoTransFunc_28
} DXVADDI_VIDEOTRANSFERFUNCTION;
```

## Constants

<table>
            
                <tr>
                    <td>DXVADDI_VideoTransFuncMask</td>
                    <td>Specifies the video transfer function mask. The first 5 (0x001F) bits of a DWORD can be used to specify the video transfer function.</td>
                </tr>
            
                <tr>
                    <td>DXVADDI_VideoTransFunc_Unknown</td>
                    <td>Specifies that the video transfer function is not specified. The default is 22_8bit_sRGB if required for a computation.</td>
                </tr>
            
                <tr>
                    <td>DXVADDI_VideoTransFunc_10</td>
                    <td>Specifies linear RGB conversion (corresponds to gamma = 1.0).</td>
                </tr>
            
                <tr>
                    <td>DXVADDI_VideoTransFunc_18</td>
                    <td>Specifies true 1.8 gamma--that is, L' = pow(L, 1/gamma) for L=0..1.</td>
                </tr>
            
                <tr>
                    <td>DXVADDI_VideoTransFunc_20</td>
                    <td>Specifies true 2.0 gamma--that is, L' = pow(L, 1/gamma) for L=0..1.</td>
                </tr>
            
                <tr>
                    <td>DXVADDI_VideoTransFunc_22</td>
                    <td>Specifies true 2.2 gamma--that is, L' = pow(L, 1/gamma) for L=0..1. 

The BT470-2 SysM primaries (that is, the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562951">DXVADDI_VIDEOPRIMARIES</a> enumeration type) use gamma 2.2.</td>
                </tr>
            
                <tr>
                    <td>DXVADDI_VideoTransFunc_709</td>
                    <td>Specifies gamma 2.2 curve with a linear range in the low range. 

The BT709, SMPTE296M, SMPTE170M, BT470, and SMPTE274M primaries (that is, the DXVADDI_VIDEOPRIMARIES enumeration type) use this video transfer function.</td>
                </tr>
            
                <tr>
                    <td>DXVADDI_VideoTransFunc_240M</td>
                    <td>Specifies gamma 2.2 curve with a linear range in the low range. 

The SMPTE240M and interim 274M primaries (that is, the DXVADDI_VIDEOPRIMARIES enumeration type) use this video transfer function.</td>
                </tr>
            
                <tr>
                    <td>DXVADDI_VideoTransFunc_sRGB</td>
                    <td>Specifies gamma 2.4 curve with a linear range in the low range, which makes it match an accurate 2.2 gamma 8-bit curve.</td>
                </tr>
            
                <tr>
                    <td>DXVADDI_VideoTransFunc_28</td>
                    <td>Specifies true 2.8 gamma--that is, L' = pow(L, 1/gamma) for L=0..1.</td>
                </tr>
</table>

## Remarks

One of the values of DXVADDI_VIDEOTRANSFERFUNCTION can be specified in the <b>VideoTransferFunction</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562904">DXVADDI_EXTENDEDFORMAT</a> structure.

DXVADDI_VIDEOTRANSFERFUNCTION corresponds to the gamma function of the data. Some transfer functions have corrections to account for 8-bit integer quantization effects.

The following constants can also be used for gamma function:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#define DXVADDI_VideoTransFunc_22_709  DXVADDI_VideoTransFunc_709
#define DXVADDI_VideoTransFunc_22_240M  DXVADDI_VideoTransFunc_240M
#define DXVADDI_VideoTransFunc_22_8bit_sRGB  DXVADDI_VideoTransFunc_sRGB</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff562904">DXVADDI_EXTENDEDFORMAT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562951">DXVADDI_VIDEOPRIMARIES</a>
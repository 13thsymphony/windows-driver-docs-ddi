---
UID : NE:d3dumddi._DXVADDI_VIDEOTRANSFERFUNCTION
title : _DXVADDI_VIDEOTRANSFERFUNCTION
author : windows-driver-content
description : The DXVADDI_VIDEOTRANSFERFUNCTION enumeration type contains values that identify the conversion function from R'G'B' to RGB.
old-location : display\dxvaddi_videotransferfunction.htm
old-project : display
ms.assetid : 8d798afe-dc75-4cd0-aad7-1f9824bdcf00
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : d3dumddi/DXVADDI_VideoTransFunc_709, DXVADDI_VideoTransFunc_22, DXVADDI_VideoTransFunc_20, DXVADDI_VideoTransFunc_18, DXVADDI_VideoTransFunc_10, DXVADDI_VideoTransFunc_240M, d3dumddi/DXVADDI_VIDEOTRANSFERFUNCTION, DXVADDI_VIDEOTRANSFERFUNCTION, _DXVADDI_VIDEOTRANSFERFUNCTION, DXVADDI_VideoTransFunc_28, DXVA2_Structs_a6fcb795-da10-4824-99b3-5f75a50a17ce.xml, d3dumddi/DXVADDI_VideoTransFunc_18, d3dumddi/DXVADDI_VideoTransFunc_240M, DXVADDI_VideoTransFunc_sRGB, d3dumddi/DXVADDI_VideoTransFunc_22, d3dumddi/DXVADDI_VideoTransFunc_10, DXVADDI_VideoTransFuncMask, d3dumddi/DXVADDI_VideoTransFunc_20, d3dumddi/DXVADDI_VideoTransFunc_sRGB, d3dumddi/DXVADDI_VideoTransFuncMask, DXVADDI_VideoTransFunc_Unknown, d3dumddi/DXVADDI_VideoTransFunc_Unknown, display.dxvaddi_videotransferfunction, DXVADDI_VIDEOTRANSFERFUNCTION enumeration [Display Devices], DXVADDI_VideoTransFunc_709, d3dumddi/DXVADDI_VideoTransFunc_28
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : d3dumddi.h
req.include-header : D3dumddi.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : DXVADDI_VIDEOTRANSFERFUNCTION
---

# _DXVADDI_VIDEOTRANSFERFUNCTION Enumeration
The DXVADDI_VIDEOTRANSFERFUNCTION enumeration type contains values that identify the conversion function from R'G'B' to RGB.

## Syntax
````
typedef enum _DXVADDI_VIDEOTRANSFERFUNCTION { 
  DXVADDI_VideoTransFuncMask      = 0x001f,
  DXVADDI_VideoTransFunc_Unknown  = 0,
  DXVADDI_VideoTransFunc_10       = 1,
  DXVADDI_VideoTransFunc_18       = 2,
  DXVADDI_VideoTransFunc_20       = 3,
  DXVADDI_VideoTransFunc_22       = 4,
  DXVADDI_VideoTransFunc_709      = 5,
  DXVADDI_VideoTransFunc_240M     = 6,
  DXVADDI_VideoTransFunc_sRGB     = 7,
  DXVADDI_VideoTransFunc_28       = 8
} DXVADDI_VIDEOTRANSFERFUNCTION;
````

## Constants

<table>

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

The BT470-2 SysM primaries (that is, the <a href="..\d3dumddi\ne-d3dumddi-_dxvaddi_videoprimaries.md">DXVADDI_VIDEOPRIMARIES</a> enumeration type) use gamma 2.2.</td>
</tr>

<tr>
<td>DXVADDI_VideoTransFunc_240M</td>
<td>Specifies gamma 2.2 curve with a linear range in the low range. 

The SMPTE240M and interim 274M primaries (that is, the DXVADDI_VIDEOPRIMARIES enumeration type) use this video transfer function.</td>
</tr>

<tr>
<td>DXVADDI_VideoTransFunc_28</td>
<td>Specifies true 2.8 gamma--that is, L' = pow(L, 1/gamma) for L=0..1.</td>
</tr>

<tr>
<td>DXVADDI_VideoTransFunc_709</td>
<td>Specifies gamma 2.2 curve with a linear range in the low range. 

The BT709, SMPTE296M, SMPTE170M, BT470, and SMPTE274M primaries (that is, the DXVADDI_VIDEOPRIMARIES enumeration type) use this video transfer function.</td>
</tr>

<tr>
<td>DXVADDI_VideoTransFunc_sRGB</td>
<td>Specifies gamma 2.4 curve with a linear range in the low range, which makes it match an accurate 2.2 gamma 8-bit curve.</td>
</tr>

<tr>
<td>DXVADDI_VideoTransFunc_Unknown</td>
<td>Specifies that the video transfer function is not specified. The default is 22_8bit_sRGB if required for a computation.</td>
</tr>

<tr>
<td>DXVADDI_VideoTransFuncMask</td>
<td>Specifies the video transfer function mask. The first 5 (0x001F) bits of a DWORD can be used to specify the video transfer function.</td>
</tr>
</table>

## Remarks

One of the values of DXVADDI_VIDEOTRANSFERFUNCTION can be specified in the <b>VideoTransferFunction</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_extendedformat.md">DXVADDI_EXTENDEDFORMAT</a> structure.

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
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\ne-d3dumddi-_dxvaddi_videoprimaries.md">DXVADDI_VIDEOPRIMARIES</a>

<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_extendedformat.md">DXVADDI_EXTENDEDFORMAT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVADDI_VIDEOTRANSFERFUNCTION enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
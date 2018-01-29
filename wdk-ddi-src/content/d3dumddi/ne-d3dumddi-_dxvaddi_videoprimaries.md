---
UID : NE:d3dumddi._DXVADDI_VIDEOPRIMARIES
title : _DXVADDI_VIDEOPRIMARIES
author : windows-driver-content
description : The DXVADDI_VIDEOPRIMARIES enumeration type contains values that identify the color primaries, which state which RGB basis functions are used.
old-location : display\dxvaddi_videoprimaries.htm
old-project : display
ms.assetid : d7049f38-78a7-42bf-a1a5-5d35fe70ae15
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : d3dumddi/DXVADDI_VIDEOPRIMARIES, d3dumddi/DXVADDI_VideoPrimaries_BT709, DXVADDI_VideoPrimaries_BT470_2_SysBG, DXVADDI_VideoPrimaries_SMPTE170M, DXVADDI_VideoPrimaries_EBU3213, DXVADDI_VideoPrimaries_BT470_2_SysM, DXVADDI_VideoPrimaries_SMPTE240M, d3dumddi/DXVADDI_VideoPrimaries_BT470_2_SysBG, DXVADDI_VideoPrimaries_SMPTE_C, DXVADDI_VideoPrimaries_BT709, d3dumddi/DXVADDI_VideoPrimariesMask, DXVADDI_VIDEOPRIMARIES enumeration [Display Devices], d3dumddi/DXVADDI_VideoPrimaries_Unknown, DXVADDI_VideoPrimariesMask, d3dumddi/DXVADDI_VideoPrimaries_reserved, d3dumddi/DXVADDI_VideoPrimaries_BT470_2_SysM, DXVADDI_VideoPrimaries_reserved, _DXVADDI_VIDEOPRIMARIES, d3dumddi/DXVADDI_VideoPrimaries_SMPTE170M, d3dumddi/DXVADDI_VideoPrimaries_SMPTE_C, d3dumddi/DXVADDI_VideoPrimaries_SMPTE240M, d3dumddi/DXVADDI_VideoPrimaries_EBU3213, DXVA2_Structs_f49dc977-3cb9-41b6-bb0c-a2de5e6a60c3.xml, display.dxvaddi_videoprimaries, DXVADDI_VIDEOPRIMARIES, DXVADDI_VideoPrimaries_Unknown
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
req.typenames : DXVADDI_VIDEOPRIMARIES
---

# _DXVADDI_VIDEOPRIMARIES Enumeration
The DXVADDI_VIDEOPRIMARIES enumeration type contains values that identify the color primaries, which state which RGB basis functions are used.

## Syntax
````
typedef enum _DXVADDI_VIDEOPRIMARIES { 
  DXVADDI_VideoPrimariesMask            = 0x001f,
  DXVADDI_VideoPrimaries_Unknown        = 0,
  DXVADDI_VideoPrimaries_reserved       = 1,
  DXVADDI_VideoPrimaries_BT709          = 2,
  DXVADDI_VideoPrimaries_BT470_2_SysM   = 3,
  DXVADDI_VideoPrimaries_BT470_2_SysBG  = 4,
  DXVADDI_VideoPrimaries_SMPTE170M      = 5,
  DXVADDI_VideoPrimaries_SMPTE240M      = 6,
  DXVADDI_VideoPrimaries_EBU3213        = 7,
  DXVADDI_VideoPrimaries_SMPTE_C        = 8
} DXVADDI_VIDEOPRIMARIES;
````

## Constants

<table>

<tr>
<td>DXVADDI_VideoPrimaries_BT470_2_SysBG</td>
<td>Specifies BT470-2 SysBG primaries.</td>
</tr>

<tr>
<td>DXVADDI_VideoPrimaries_BT470_2_SysM</td>
<td>Specifies BT470-2 SysM primaries, which are the original NTSC primaries.</td>
</tr>

<tr>
<td>DXVADDI_VideoPrimaries_BT709</td>
<td>Specifies BT709 primaries (including sRGB and scRGB).</td>
</tr>

<tr>
<td>DXVADDI_VideoPrimaries_EBU3213</td>
<td>Specifies EBU3213 primaries.</td>
</tr>

<tr>
<td>DXVADDI_VideoPrimaries_reserved</td>
<td>[in] Reserved. Do not use this value.</td>
</tr>

<tr>
<td>DXVADDI_VideoPrimaries_SMPTE_C</td>
<td>Specifies SMPTE_C primaries, which are analog '79 NTSC primaries.</td>
</tr>

<tr>
<td>DXVADDI_VideoPrimaries_SMPTE170M</td>
<td>Specifies SMPTE170M primaries, which are rarely used analog NTSC primaries (also known as SMPTE RP 145).</td>
</tr>

<tr>
<td>DXVADDI_VideoPrimaries_SMPTE240M</td>
<td>Specifies SMPTE240M primaries.</td>
</tr>

<tr>
<td>DXVADDI_VideoPrimaries_Unknown</td>
<td>Specifies that color primaries are not specified. The default is BT709.</td>
</tr>

<tr>
<td>DXVADDI_VideoPrimariesMask</td>
<td>Specifies the color primaries mask. The first 5 (0x001F) bits of a DWORD can be used to specify color primaries.</td>
</tr>
</table>

## Remarks

One of the values of DXVADDI_VIDEOPRIMARIES can be specified in the <b>VideoPrimaries</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_extendedformat.md">DXVADDI_EXTENDEDFORMAT</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_extendedformat.md">DXVADDI_EXTENDEDFORMAT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVADDI_VIDEOPRIMARIES enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
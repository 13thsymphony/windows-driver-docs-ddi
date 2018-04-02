---
UID: NE:dxva._DXVA_NominalRange
title: "_DXVA_NominalRange"
author: windows-driver-content
description: The DXVA_NominalRange enumeration type contains enumerators that identify whether sample data includes headroom (values beyond 1.0 white) and toeroom (superblacks below the reference 0.0 black).
old-location: display\dxva_nominalrange.htm
old-project: display
ms.assetid: 9e319f9d-4c24-4dd3-b5a1-b244714c06dc
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXVA_NominalRange, DXVA_NominalRange enumeration [Display Devices], DXVA_NominalRangeMask, DXVA_NominalRangeShift, DXVA_NominalRange_0_255, DXVA_NominalRange_16_235, DXVA_NominalRange_48_208, DXVA_NominalRange_Normal, DXVA_NominalRange_Unknown, DXVA_NominalRange_Wide, _DXVA_NominalRange, display.dxva_nominalrange, dxva/DXVA_NominalRange, dxva/DXVA_NominalRangeMask, dxva/DXVA_NominalRangeShift, dxva/DXVA_NominalRange_0_255, dxva/DXVA_NominalRange_16_235, dxva/DXVA_NominalRange_48_208, dxva/DXVA_NominalRange_Normal, dxva/DXVA_NominalRange_Unknown, dxva/DXVA_NominalRange_Wide, dxvaref_5931dd2e-baac-48a6-931a-b7f3fc965b4d.xml
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
-	DXVA_NominalRange
product: Windows
targetos: Windows
req.typenames: DXVA_NominalRange
---

# _DXVA_NominalRange Enumeration
The DXVA_NominalRange enumeration type contains enumerators that identify whether sample data includes headroom (values beyond 1.0 white) and toeroom (superblacks below the reference 0.0 black).

## Syntax
```
typedef enum _DXVA_NominalRange {
  DXVA_NominalRangeShift     ,
  DXVA_NominalRangeMask      ,
  DXVA_NominalRange_Unknown  ,
  DXVA_NominalRange_Normal   ,
  DXVA_NominalRange_Wide     ,
  DXVA_NominalRange_0_255    ,
  DXVA_NominalRange_16_235   ,
  DXVA_NominalRange_48_208
} DXVA_NominalRange;
```

## Constants

<table>
            
                <tr>
                    <td>DXVA_NominalRangeShift</td>
                    <td>Specifies to shift bits by 12 positions (DXVA_ExtColorData_ShiftBase + 4, or 8 + 4).</td>
                </tr>
            
                <tr>
                    <td>DXVA_NominalRangeMask</td>
                    <td>Specifies the nominal range mask. 3 (0x00007000) bits of a DWORD can be used to specify nominal range.</td>
                </tr>
            
                <tr>
                    <td>DXVA_NominalRange_Unknown</td>
                    <td>Specifies that the nominal range is not specified.</td>
                </tr>
            
                <tr>
                    <td>DXVA_NominalRange_Normal</td>
                    <td>Specifies that normalized chroma [0..1] maps to [0..255] (8bit) or [0..1023] (10 bit).</td>
                </tr>
            
                <tr>
                    <td>DXVA_NominalRange_Wide</td>
                    <td>Specifies that normalized chroma [0..1] maps to [16..235] (8bit) or [64..940] (10 bit).</td>
                </tr>
            
                <tr>
                    <td>DXVA_NominalRange_0_255</td>
                    <td>Specifies that normalized chroma [0..1] maps to [0..255] (8bit) or [0..1023] (10 bit).</td>
                </tr>
            
                <tr>
                    <td>DXVA_NominalRange_16_235</td>
                    <td>Specifies that normalized chroma [0..1] maps to [16..235] (8bit) or [64..940] (10 bit).</td>
                </tr>
            
                <tr>
                    <td>DXVA_NominalRange_48_208</td>
                    <td>Specifies that normalized chroma [0..1] maps to [48..208] (8bit) or [192..832] (10 bit).</td>
                </tr>
</table>

## Remarks

One of the enumerators of DXVA_NominalRange can be specified in the <b>NominalRange</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563967">DXVA_ExtendedFormat</a> structure.

Wide gamut R'G'B' (that is, blackpoint at 16,16,16 and whitepoint at 235,235,235) must be differentiated from normal <a href="http://go.microsoft.com/fwlink/p/?linkid=10112">sRGB</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | This enumeration type applies only to Windows Server 2003 with SP1 and later, and Windows XP with SP2 and later. This enumeration type applies only to Windows Server 2003 with SP1 and later, and Windows XP with SP2 and later. |
| **Header** | dxva.h (include Dxva.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563967">DXVA_ExtendedFormat</a>
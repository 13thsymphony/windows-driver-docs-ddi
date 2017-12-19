---
UID: NE.d3dumddi._DXVADDI_VIDEOPRIMARIES
title: _DXVADDI_VIDEOPRIMARIES
author: windows-driver-content
description: The DXVADDI_VIDEOPRIMARIES enumeration type contains values that identify the color primaries, which state which RGB basis functions are used.
old-location: display\dxvaddi_videoprimaries.htm
old-project: display
ms.assetid: d7049f38-78a7-42bf-a1a5-5d35fe70ae15
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DXVADDI_VIDEOPRIMARIES, DXVADDI_VIDEOPRIMARIES
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
req.alt-api: DXVADDI_VIDEOPRIMARIES
req.alt-loc: d3dumddi.h
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
---

# _DXVADDI_VIDEOPRIMARIES enumeration



## -description
The DXVADDI_VIDEOPRIMARIES enumeration type contains values that identify the color primaries, which state which RGB basis functions are used.



## -syntax

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


## -enum-fields

### -field DXVADDI_VideoPrimariesMask

Specifies the color primaries mask. The first 5 (0x001F) bits of a DWORD can be used to specify color primaries.


### -field DXVADDI_VideoPrimaries_Unknown

Specifies that color primaries are not specified. The default is BT709.


### -field DXVADDI_VideoPrimaries_reserved

[in] Reserved. Do not use this value.


### -field DXVADDI_VideoPrimaries_BT709

Specifies BT709 primaries (including sRGB and scRGB).


### -field DXVADDI_VideoPrimaries_BT470_2_SysM

Specifies BT470-2 SysM primaries, which are the original NTSC primaries. 


### -field DXVADDI_VideoPrimaries_BT470_2_SysBG

Specifies BT470-2 SysBG primaries. 


### -field DXVADDI_VideoPrimaries_SMPTE170M

Specifies SMPTE170M primaries, which are rarely used analog NTSC primaries (also known as SMPTE RP 145).


### -field DXVADDI_VideoPrimaries_SMPTE240M

Specifies SMPTE240M primaries. 


### -field DXVADDI_VideoPrimaries_EBU3213

Specifies EBU3213 primaries. 


### -field DXVADDI_VideoPrimaries_SMPTE_C

Specifies SMPTE_C primaries, which are analog '79 NTSC primaries.


## -remarks
One of the values of DXVADDI_VIDEOPRIMARIES can be specified in the <b>VideoPrimaries</b> member of the <a href="display.dxvaddi_extendedformat">DXVADDI_EXTENDEDFORMAT</a> structure.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.dxvaddi_extendedformat">DXVADDI_EXTENDEDFORMAT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVADDI_VIDEOPRIMARIES enumeration%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


---
UID: NS:d3dumddi._DXVADDI_FREQUENCY
title: "_DXVADDI_FREQUENCY"
author: windows-driver-content
description: The DXVADDI_FREQUENCY structure describes the video frame rate in Hertz (Hz). For example, NTSC TV is 60000 over 1001.
old-location: display\dxvaddi_frequency.htm
old-project: display
ms.assetid: 5bfb02f6-4482-4260-827f-54c5f74b6b46
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXVA2_Structs_bf2ee217-d321-4302-8bd3-1621081fdb09.xml, DXVADDI_FREQUENCY, DXVADDI_FREQUENCY structure [Display Devices], _DXVADDI_FREQUENCY, d3dumddi/DXVADDI_FREQUENCY, display.dxvaddi_frequency
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	DXVADDI_FREQUENCY
product: Windows
targetos: Windows
req.typenames: DXVADDI_FREQUENCY
---

# _DXVADDI_FREQUENCY structure
The DXVADDI_FREQUENCY structure describes the video frame rate in Hertz (Hz). For example, NTSC TV is 60000 over 1001.

## Syntax
```
typedef struct _DXVADDI_FREQUENCY {
  UINT Numerator;
  UINT Denominator;
} DXVADDI_FREQUENCY;
```

## Members


`Numerator`

[in] The numerator of the frequency fraction.

`Denominator`

[in] The denominator of the frequency fraction.

## Remarks
The user-mode display driver must interpret the video frame rate for the following special cases as indicated:

<ul>
<li>
<b>Numerator</b>/<b>Denominator</b> = 0/0 is interpreted as an unknown frequency.

</li>
<li>
<b>Numerator</b>/<b>Denominator</b> = n/0, where n is any number, is interpreted as invalid.

</li>
<li>
<b>Numerator</b>/<b>Denominator</b> = 0/n is interpreted as zero frequency.

</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff562944">DXVADDI_VIDEODESC</a>
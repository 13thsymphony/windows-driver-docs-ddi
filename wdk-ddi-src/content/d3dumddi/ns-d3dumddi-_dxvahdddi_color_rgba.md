---
UID: NS.D3DUMDDI._DXVAHDDDI_COLOR_RGBA
title: _DXVAHDDDI_COLOR_RGBA
author: windows-driver-content
description: The DXVAHDDDI_COLOR_RGBA structure describes color in RGB terms.
old-location: display\dxvahdddi_color_rgba.htm
old-project: display
ms.assetid: 73779eb1-514e-4103-9af2-0dc0c86cb04e
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DXVAHDDDI_COLOR_RGBA, DXVAHDDDI_COLOR_RGBA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_COLOR_RGBA is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXVAHDDDI_COLOR_RGBA
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

# _DXVAHDDDI_COLOR_RGBA structure



## -description
The DXVAHDDDI_COLOR_RGBA structure describes color in RGB terms.  



## -syntax

````
typedef struct _DXVAHDDDI_COLOR_RGBA {
  FLOAT R;
  FLOAT G;
  FLOAT B;
  FLOAT A;
} DXVAHDDDI_COLOR_RGBA;
````


## -struct-fields

### -field R

[in] A FLOAT value in the 0.0 to 1.0 range that is used to describe the red component of the RGB color. 


### -field G

[in] A FLOAT value in the 0.0 to 1.0 range that is used to describe the green component of the RGB color.


### -field B

[in] A FLOAT value in the 0.0 to 1.0 range that is used to describe the blue component of the RGB color.


### -field A

[in] A FLOAT value in the 0.0 to 1.0 range that is used to describe the alpha component (that is, the transparency level) of the RGB color.


## -remarks
The setting of DXVAHDDDI_COLOR_RGBA for full range RGB black with opaque alpha is (0.0, 0.0, 0.0, 1.0). The setting of DXVAHDDDI_COLOR_RGBA for limited range RGB black with half transparent alpha is (0.0625, 0.0625, 0.0625, 0.5), which is (0, 0, 0, 255) and (16, 16, 16, 128) respectively when 8-bit presentation is used.

R, G, and B values can be out of the [0.0, 1.0] range for wide gamut format (for example, for XR_BIAS, FP16, and FP32 formats).

A DXVAHDDDI_COLOR_YCbCrA structure is specified in the <b>RGB</b> member of the <a href="display.dxvahdddi_color">DXVAHDDDI_COLOR</a> union to specify the color in RGB terms.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
DXVAHDDDI_COLOR_RGBA is supported beginning with the Windows 7 operating system.

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
<a href="display.dxvahdddi_color">DXVAHDDDI_COLOR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVAHDDDI_COLOR_RGBA structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


---
UID: NS.D3DUMDDI._DXVAHDDDI_COLOR_YCBCRA
title: _DXVAHDDDI_COLOR_YCbCrA
author: windows-driver-content
description: The DXVAHDDDI_COLOR_YCbCrA structure describes color in YCbCr terms.
old-location: display\dxvahdddi_color_ycbcra.htm
old-project: display
ms.assetid: e2a624e9-599e-4325-820b-945b3e649323
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _DXVAHDDDI_COLOR_YCbCrA, DXVAHDDDI_COLOR_YCbCrA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_COLOR_YCbCrA is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXVAHDDDI_COLOR_YCbCrA
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

# _DXVAHDDDI_COLOR_YCbCrA structure



## -description
The DXVAHDDDI_COLOR_YCbCrA structure describes color in YCbCr terms.  


## -syntax

````
typedef struct _DXVAHDDDI_COLOR_YCbCrA {
  FLOAT Y;
  FLOAT Cb;
  FLOAT Cr;
  FLOAT A;
} DXVAHDDDI_COLOR_YCbCrA;
````


## -struct-fields

### -field Y

[in] A FLOAT value in the 0.0 to 1.0 range that is used to describe the luma component of the YCbCr color. 

### -field Cb

[in] A FLOAT value in the 0.0 to 1.0 range that is used to describe the blue chroma component of the YCbCr color. 

### -field Cr

[in] A FLOAT value in the 0.0 to 1.0 range that is used to describe the red chroma component of the YCbCr color. 

### -field A

[in] A FLOAT value in the 0.0 to 1.0 range that is used to describe the alpha component (that is, the transparency level) of the YCbCr color.

## -remarks
The setting of DXVAHDDDI_COLOR_YCbCrA for YCbCr black with opaque alpha is (0.0625, 0.5, 0.5, 1.0), which is (16, 128, 128, 255) when 8-bit presentation is used.

A DXVAHDDDI_COLOR_YCbCrA structure is specified in the <b>YCbCr</b> member of the <a href="display.dxvahdddi_color">DXVAHDDDI_COLOR</a> union to specify the color in YCbCr terms.

## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
DXVAHDDDI_COLOR_YCbCrA is supported beginning with the Windows 7 operating system.
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
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVAHDDDI_COLOR_YCbCrA structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

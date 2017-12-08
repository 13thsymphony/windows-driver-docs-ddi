---
UID: NE.icm.COLORTYPE
title: COLORTYPE
author: windows-driver-content
description: The values of the COLORTYPE enumeration are used by WCS functions to indicate the format of vector content. Most values have equivalent structures that are contained in the ICM COLOR structure (described in the Microsoft Windows SDK documentation).
old-location: print\colortype.htm
old-project: print
ms.assetid: aa7d8d32-7bbe-4091-82a2-32ade463dd9e
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: COLORTYPE, COLORTYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: icm.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Included in Windows Vista and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: COLORTYPE
req.alt-loc: icm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# COLORTYPE enumeration



## -description
The values of the COLORTYPE enumeration are used by WCS functions to indicate the format of vector content. Most values have equivalent structures that are contained in the ICM COLOR structure (described in the Microsoft Windows SDK documentation).


## -syntax

````
typedef enum  { 
  COLOR_GRAY       = 1,
  COLOR_RGB        = 2,
  COLOR_XYZ        = 3,
  COLOR_Yxy        = 4,
  COLOR_Lab        = 5,
  COLOR_3_CHANNEL  = 6,
  COLOR_CMYK       = 7,
  COLOR_5_CHANNEL  = 8,
  COLOR_6_CHANNEL  = 9,
  COLOR_7_CHANNEL  = 10,
  COLOR_8_CHANNEL  = 11,
  COLOR_NAMED      = 12
} COLORTYPE;
````


## -enum-fields

### -field COLOR_GRAY

Specifies a 16-bit gray-scale pixel value. Correlates to the ICM GRAYCOLOR.

### -field COLOR_RGB

Specifies a 48-bit RGB pixel value. Correlates to the ICM RGBCOLOR structure.

### -field COLOR_XYZ

Specifies a 48-bit CIEXYZ pixel value. Correlates to the ICM XYZCOLOR structure.

### -field COLOR_Yxy

Specifies a 48-bit CIE Yxy pixel value. Correlates to the ICM YxyCOLOR structure.

### -field COLOR_Lab

Specifies a 48-bit CIELAB pixel value. Correlates to the ICM LabCOLOR structure.

### -field COLOR_3_CHANNEL

Specifies a 48-bit generic three-channel pixel value. Correlates to the ICM GENERIC3CHANNEL structure.

### -field COLOR_CMYK

Specifies a 48-bit CMYK pixel value. Correlates to the ICM CMYKCOLOR structure.

### -field COLOR_5_CHANNEL

Specifies a 64-bit generic five-channel pixel value.

### -field COLOR_6_CHANNEL

Specifies a 64-bit generic six-channel pixel value.

### -field COLOR_7_CHANNEL

Specifies a 64-bit generic seven-channel pixel value.

### -field COLOR_8_CHANNEL

Specifies a 64-bit generic eight-channel pixel value.

### -field COLOR_NAMED

Specifies a 32-bit named color-indexed pixel value. Correlates to the ICM NAMEDCOLOR structure.

## -remarks
In addition to managing the common two, three, and four channel color spaces, ICM 2.0 and WCS are able to perform color management with device profiles that contain five through eight color channels. ICM 2.0 and WCS are also able to use named color spaces. When five, six, seven, or eight color channels are used, the provider of the device profile is free to determine what the color channels represent. The same is true of named color spaces. ICM 2.0 and WCS are able to manage these color spaces as long as there is a mapping in the device profile that maps the channels or the name space to the Profile Connection Space (PCS). The device profile must also contain a mapping from the PCS into the five, six, seven, or eight channel spaces, or into the named color space.

The PCOLORTYPE and LPCOLORTYPE data types are defined as pointers to this enumeration:

## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Included in Windows Vista and later.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Icm.h</dt>
</dl>
</td>
</tr>
</table>
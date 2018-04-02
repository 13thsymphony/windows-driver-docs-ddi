---
UID: NE:icm.COLORDATATYPE
title: COLORDATATYPE
author: windows-driver-content
description: The values of the COLORDATATYPE enumeration are used by WCS functions to indicate the data type of vector content.
old-location: print\colordatatype.htm
old-project: print
ms.assetid: ff7c9a81-3445-4a9e-aee3-2c63aafb0c82
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PCOLORDATATYPE, COLORDATATYPE, COLORDATATYPE enumeration [Print Devices], COLOR_10b_R10G10B10A2, COLOR_10b_R10G10B10A2_XR, COLOR_BYTE, COLOR_FLOAT, COLOR_FLOAT16, COLOR_S2DOT13FIXED, COLOR_WORD, colorfnc_6619f1aa-d905-47ef-bd39-2fe34446e831.xml, icm/COLORDATATYPE, icm/COLOR_10b_R10G10B10A2, icm/COLOR_10b_R10G10B10A2_XR, icm/COLOR_BYTE, icm/COLOR_FLOAT, icm/COLOR_FLOAT16, icm/COLOR_S2DOT13FIXED, icm/COLOR_WORD, print.colordatatype"
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
-	icm.h
api_name:
-	COLORDATATYPE
product: Windows
targetos: Windows
req.typenames: COLORDATATYPE
---

# COLORDATATYPE Enumeration
The values of the COLORDATATYPE enumeration are used by WCS functions to indicate the data type of vector content.

## Syntax
```
typedef enum COLORDATATYPE {
  COLOR_BYTE                ,
  COLOR_WORD                ,
  COLOR_FLOAT               ,
  COLOR_S2DOT13FIXED        ,
  COLOR_10b_R10G10B10A2     ,
  COLOR_10b_R10G10B10A2_XR  ,
  COLOR_FLOAT16
} ;
```

## Constants

<table>
            
                <tr>
                    <td>COLOR_BYTE</td>
                    <td>Color data is stored as 8 bits per channel, with a value from 0 to 255, inclusive.</td>
                </tr>
            
                <tr>
                    <td>COLOR_WORD</td>
                    <td>Color data is stored as 16 bits per channel, with a value from 0 to 65535, inclusive.</td>
                </tr>
            
                <tr>
                    <td>COLOR_FLOAT</td>
                    <td>Color data is stored as 32 bits value per channel, as defined by the IEEE 32-bit floating point standard.</td>
                </tr>
            
                <tr>
                    <td>COLOR_S2DOT13FIXED</td>
                    <td>Color data is stored as 16 bits per channel, with a fixed range of -4 to +4, inclusive. A signed format is used, with 1 bit for the sign, 2 bits for the integer portion, and 13 bits for the fractional portion.</td>
                </tr>
            
                <tr>
                    <td>COLOR_10b_R10G10B10A2</td>
                    <td>Packed WORD per channel. data range [0, 1]</td>
                </tr>
            
                <tr>
                    <td>COLOR_10b_R10G10B10A2_XR</td>
                    <td>Packed extended range WORD per channel. data range [-1, 3]</td>
                </tr>
            
                <tr>
                    <td>COLOR_FLOAT16</td>
                    <td>FLOAT16 per channel.</td>
                </tr>
</table>

## Remarks

The PCOLORDATATYPE and LPCOLORDATATYPE data types are defined as pointers to this enumeration:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef COLORDATATYPE *PCOLORDATATYPE, *LPCOLORDATATYPE;</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Included in Windows Vista and later. Included in Windows Vista and later. |
| **Header** | icm.h |
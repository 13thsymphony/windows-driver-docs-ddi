---
UID: NE:icm.COLORDATATYPE
title: COLORDATATYPE
author: windows-driver-content
description: The values of the COLORDATATYPE enumeration are used by WCS functions to indicate the data type of vector content.
old-location: print\colordatatype.htm
old-project: print
ms.assetid: ff7c9a81-3445-4a9e-aee3-2c63aafb0c82
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: COLORDATATYPE, COLORDATATYPE, *PCOLORDATATYPE
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
req.alt-api: COLORDATATYPE
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
req.typenames: COLORDATATYPE
---

# COLORDATATYPE enumeration



## -description
The values of the COLORDATATYPE enumeration are used by WCS functions to indicate the data type of vector content.



## -syntax

````
typedef enum  { 
  COLOR_BYTE                = 1,
  COLOR_WORD                = 2,
  COLOR_FLOAT               = 3,
  COLOR_S2DOT13FIXED        = 4,
  COLOR_10b_R10G10B10A2     = 5,
  COLOR_10b_R10G10B10A2_XR  = 6,
  COLOR_FLOAT16             = 7
} COLORDATATYPE;
````


## -enum-fields

### -field COLOR_BYTE

Color data is stored as 8 bits per channel, with a value from 0 to 255, inclusive.


### -field COLOR_WORD

Color data is stored as 16 bits per channel, with a value from 0 to 65535, inclusive.


### -field COLOR_FLOAT

Color data is stored as 32 bits value per channel, as defined by the IEEE 32-bit floating point standard.


### -field COLOR_S2DOT13FIXED

Color data is stored as 16 bits per channel, with a fixed range of -4 to +4, inclusive. A signed format is used, with 1 bit for the sign, 2 bits for the integer portion, and 13 bits for the fractional portion.


### -field COLOR_10b_R10G10B10A2

Packed WORD per channel. data range [0, 1]


### -field COLOR_10b_R10G10B10A2_XR

Packed extended range WORD per channel. data range [-1, 3]


### -field COLOR_FLOAT16

FLOAT16 per channel.


## -remarks
The PCOLORDATATYPE and LPCOLORDATATYPE data types are defined as pointers to this enumeration:


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
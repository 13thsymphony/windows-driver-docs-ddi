---
UID: NE:d3dukmdt._D3DDDIMULTISAMPLE_TYPE
title: _D3DDDIMULTISAMPLE_TYPE
author: windows-driver-content
description: The D3DDDIMULTISAMPLE_TYPE enumeration defines the levels of full-scene multisampling that the device can apply.
old-location: display\d3dddimultisample_type.htm
old-project: display
ms.assetid: aba3b4fd-92e4-4551-9396-ee34e38ecfd6
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DDDIMULTISAMPLE_TYPE, D3DDDIMULTISAMPLE_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dukmdt.h
req.include-header: D3dukmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDIMULTISAMPLE_TYPE
req.alt-loc: d3dukmdt.h
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
req.typenames: D3DDDIMULTISAMPLE_TYPE
---

# _D3DDDIMULTISAMPLE_TYPE enumeration



## -description
The D3DDDIMULTISAMPLE_TYPE enumeration defines the levels of full-scene multisampling that the device can apply.



## -syntax

````
typedef enum _D3DDDIMULTISAMPLE_TYPE { 
  D3DDDIMULTISAMPLE_NONE         = 0,
  D3DDDIMULTISAMPLE_NONMASKABLE  = 1,
  D3DDDIMULTISAMPLE_2_SAMPLES    = 2,
  D3DDDIMULTISAMPLE_3_SAMPLES    = 3,
  D3DDDIMULTISAMPLE_4_SAMPLES    = 4,
  D3DDDIMULTISAMPLE_5_SAMPLES    = 5,
  D3DDDIMULTISAMPLE_6_SAMPLES    = 6,
  D3DDDIMULTISAMPLE_7_SAMPLES    = 7,
  D3DDDIMULTISAMPLE_8_SAMPLES    = 8,
  D3DDDIMULTISAMPLE_9_SAMPLES    = 9,
  D3DDDIMULTISAMPLE_10_SAMPLES   = 10,
  D3DDDIMULTISAMPLE_11_SAMPLES   = 11,
  D3DDDIMULTISAMPLE_12_SAMPLES   = 12,
  D3DDDIMULTISAMPLE_13_SAMPLES   = 13,
  D3DDDIMULTISAMPLE_14_SAMPLES   = 14,
  D3DDDIMULTISAMPLE_15_SAMPLES   = 15,
  D3DDDIMULTISAMPLE_16_SAMPLES   = 16,
  D3DDDIMULTISAMPLE_FORCE_UINT   = 0x7fffffff
} D3DDDIMULTISAMPLE_TYPE;
````


## -enum-fields

### -field D3DDDIMULTISAMPLE_NONE

The level of full-scene multisampling available.


### -field D3DDDIMULTISAMPLE_NONMASKABLE

The level of full-scene multisampling available.


### -field D3DDDIMULTISAMPLE_2_SAMPLES

The level of full-scene multisampling available.


### -field D3DDDIMULTISAMPLE_3_SAMPLES

The level of full-scene multisampling available.


### -field D3DDDIMULTISAMPLE_4_SAMPLES

The level of full-scene multisampling available.


### -field D3DDDIMULTISAMPLE_5_SAMPLES

The level of full-scene multisampling available.


### -field D3DDDIMULTISAMPLE_6_SAMPLES

The level of full-scene multisampling available.


### -field D3DDDIMULTISAMPLE_7_SAMPLES

The level of full-scene multisampling available.


### -field D3DDDIMULTISAMPLE_8_SAMPLES

The level of full-scene multisampling available.


### -field D3DDDIMULTISAMPLE_9_SAMPLES

The level of full-scene multisampling available.


### -field D3DDDIMULTISAMPLE_10_SAMPLES

The level of full-scene multisampling available.


### -field D3DDDIMULTISAMPLE_11_SAMPLES

The level of full-scene multisampling available.


### -field D3DDDIMULTISAMPLE_12_SAMPLES

The level of full-scene multisampling available.


### -field D3DDDIMULTISAMPLE_13_SAMPLES

The level of full-scene multisampling available.


### -field D3DDDIMULTISAMPLE_14_SAMPLES

The level of full-scene multisampling available.


### -field D3DDDIMULTISAMPLE_15_SAMPLES

The level of full-scene multisampling available.


### -field D3DDDIMULTISAMPLE_16_SAMPLES

The level of full-scene multisampling available.


### -field D3DDDIMULTISAMPLE_FORCE_UINT

Forces this enumeration to compile to 32 bits in size. Without this value, some compilers would allow this enumeration to compile to a size other than 32 bits. This value is not used.


## -remarks


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
<dt>D3dukmdt.h (include D3dukmdt.h)</dt>
</dl>
</td>
</tr>
</table>
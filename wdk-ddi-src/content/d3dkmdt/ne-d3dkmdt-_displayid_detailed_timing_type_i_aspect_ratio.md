---
UID : NE:d3dkmdt._DISPLAYID_DETAILED_TIMING_TYPE_I_ASPECT_RATIO
title : _DISPLAYID_DETAILED_TIMING_TYPE_I_ASPECT_RATIO
author : windows-driver-content
description : The DISPLAYID_DETAILED_TIMING_TYPE_I_ASPECT_RATIO enumeration indicates the display device's aspect ratio, defined as width by height (width x height).
old-location : display\displayid_detailed_timing_type_i_aspect_ratio.htm
old-project : display
ms.assetid : 2641a446-1890-4b7d-ac28-c72338207f87
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _DISPLAYID_DETAILED_TIMING_TYPE_I_ASPECT_RATIO,
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : d3dkmdt.h
req.include-header : D3dkmdt.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows 7 and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : _DISPLAYID_DETAILED_TIMING_TYPE_I_ASPECT_RATIO
req.alt-loc : d3dkmdt.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : 
---

# _DISPLAYID_DETAILED_TIMING_TYPE_I_ASPECT_RATIO Enumeration
The DISPLAYID_DETAILED_TIMING_TYPE_I_ASPECT_RATIO enumeration indicates the display device's aspect ratio, defined as width by height (width x height).

## Syntax
````
enum _DISPLAYID_DETAILED_TIMING_TYPE_I_ASPECT_RATIO {
  DIDDT1_AspectRatio_1x1    = 0, 
  DIDDT1_AspectRatio_5x4    = 1, 
  DIDDT1_AspectRatio_4x3    = 2, 
  DIDDT1_AspectRatio_15x9   = 3, 
  DIDDT1_AspectRatio_16x9   = 4, 
  DIDDT1_AspectRatio_16x10  = 5 

};
````

## Constants

<table>

<tr>
<td>DIDDT1_AspectRatio_15x9</td>
<td>Indicates a 15 x 9 aspect ratio.</td>
</tr>

<tr>
<td>DIDDT1_AspectRatio_16x10</td>
<td>Indicates a 16 x 10 aspect ratio.</td>
</tr>

<tr>
<td>DIDDT1_AspectRatio_16x9</td>
<td>Indicates a 16 x 9 aspect ratio.</td>
</tr>

<tr>
<td>DIDDT1_AspectRatio_1x1</td>
<td>Indicates a 1 x 1 aspect ratio.</td>
</tr>

<tr>
<td>DIDDT1_AspectRatio_4x3</td>
<td>Indicates a 4 x 3 aspect ratio.</td>
</tr>

<tr>
<td>DIDDT1_AspectRatio_5x4</td>
<td>Indicates a 5 x 4 aspect ratio.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dkmdt.h (include D3dkmdt.h) |
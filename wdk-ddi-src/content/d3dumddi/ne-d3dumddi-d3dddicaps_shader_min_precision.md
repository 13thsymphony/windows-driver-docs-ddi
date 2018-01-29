---
UID : NE:d3dumddi.D3DDDICAPS_SHADER_MIN_PRECISION
title : D3DDDICAPS_SHADER_MIN_PRECISION
author : windows-driver-content
description : Specifies minimum precision levels that the user-mode driver supports in shaders.
old-location : display\d3dddicaps_shader_min_precision.htm
old-project : display
ms.assetid : 98856726-b426-42e4-9560-f6b56164824a
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.d3dddicaps_shader_min_precision, D3DDDICAPS_SHADER_MIN_PRECISION, d3dumddi/D3DDDICAPS_SHADER_MIN_PRECISION_16_BIT, d3dumddi/D3DDDICAPS_SHADER_MIN_PRECISION, D3DDDICAPS_SHADER_MIN_PRECISION_16_BIT, D3DDDICAPS_SHADER_MIN_PRECISION enumeration [Display Devices], D3DDDICAPS_SHADER_MIN_PRECISION_10_BIT, d3dumddi/D3DDDICAPS_SHADER_MIN_PRECISION_10_BIT
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : d3dumddi.h
req.include-header : D3dumddi.h
req.target-type : Windows
req.target-min-winverclnt : Windows 8
req.target-min-winversvr : Windows Server 2012
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : D3DDDICAPS_SHADER_MIN_PRECISION
---

# D3DDDICAPS_SHADER_MIN_PRECISION Enumeration
Specifies minimum precision levels that the user-mode driver supports in shaders.

## Syntax
````
typedef enum D3DDDICAPS_SHADER_MIN_PRECISION { 
  D3DDDICAPS_SHADER_MIN_PRECISION_10_BIT  = 0x1,
  D3DDDICAPS_SHADER_MIN_PRECISION_16_BIT  = 0x2
} D3DDDICAPS_SHADER_MIN_PRECISION;
````

## Constants

<table>

<tr>
<td>D3DDDICAPS_SHADER_MIN_PRECISION_10_BIT</td>
<td>The minimum precision level is 10-bit.</td>
</tr>

<tr>
<td>D3DDDICAPS_SHADER_MIN_PRECISION_16_BIT</td>
<td>The minimum precision level is 16-bit.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dumddi.h (include D3dumddi.h) |
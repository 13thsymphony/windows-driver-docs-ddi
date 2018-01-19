---
UID : NE:d3d10umddi.D3D10_DDI_COMPARISON_FUNC
title : D3D10_DDI_COMPARISON_FUNC
author : windows-driver-content
description : The D3D10_DDI_COMPARISON_FUNC enumeration type contains values that identify the comparison function to perform.
old-location : display\d3d10_ddi_comparison_func.htm
old-project : display
ms.assetid : 32a823e2-324a-45f3-82ad-e9f99749dc85
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3D10_DDI_COMPARISON_FUNC, D3D10_DDI_COMPARISON_FUNC
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : d3d10umddi.h
req.include-header : D3d10umddi.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : D3D10_DDI_COMPARISON_FUNC
req.alt-loc : d3d10umddi.h
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
req.typenames : D3D10_DDI_COMPARISON_FUNC
---

# D3D10_DDI_COMPARISON_FUNC Enumeration
The D3D10_DDI_COMPARISON_FUNC enumeration type contains values that identify the comparison function to perform.

## Syntax
````
typedef enum D3D10_DDI_COMPARISON_FUNC { 
  D3D10_DDI_COMPARISON_NEVER          = 1,
  D3D10_DDI_COMPARISON_LESS           = 2,
  D3D10_DDI_COMPARISON_EQUAL          = 3,
  D3D10_DDI_COMPARISON_LESS_EQUAL     = 4,
  D3D10_DDI_COMPARISON_GREATER        = 5,
  D3D10_DDI_COMPARISON_NOT_EQUAL      = 6,
  D3D10_DDI_COMPARISON_GREATER_EQUAL  = 7,
  D3D10_DDI_COMPARISON_ALWAYS         = 8
} D3D10_DDI_COMPARISON_FUNC;
````

## Constants

<table>

<tr>
<td>D3D10_DDI_COMPARISON_ALWAYS</td>
<td>The comparison always succeeds.</td>
</tr>

<tr>
<td>D3D10_DDI_COMPARISON_EQUAL</td>
<td>The comparison is an equal-to operation.</td>
</tr>

<tr>
<td>D3D10_DDI_COMPARISON_GREATER</td>
<td>The comparison is a greater-than operation.</td>
</tr>

<tr>
<td>D3D10_DDI_COMPARISON_GREATER_EQUAL</td>
<td>The comparison is a greater-than or equal-to operation.</td>
</tr>

<tr>
<td>D3D10_DDI_COMPARISON_LESS</td>
<td>The comparison is a less-than operation.</td>
</tr>

<tr>
<td>D3D10_DDI_COMPARISON_LESS_EQUAL</td>
<td>The comparison is a less-than or equal-to operation.</td>
</tr>

<tr>
<td>D3D10_DDI_COMPARISON_NEVER</td>
<td>The comparison never succeeds.</td>
</tr>

<tr>
<td>D3D10_DDI_COMPARISON_NOT_EQUAL</td>
<td>The comparison is a not-equal-to operation.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<dl>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d10_ddi_depth_stencil_desc.md">D3D10_DDI_DEPTH_STENCIL_DESC</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d10_ddi_depth_stencilop_desc.md">D3D10_DDI_DEPTH_STENCILOP_DESC</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10_DDI_COMPARISON_FUNC enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
---
UID : NE:d3dkmdt._D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE
title : _D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE
author : windows-driver-content
description : The D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE enumeration indicates the pivot type in a call to DxgkDdiEnumVidPnCofuncModality.
old-location : display\d3dkmdt_enumcofuncmodality_pivot_type.htm
old-project : display
ms.assetid : ba99936a-e76a-4a34-b7cd-762a8f15732c
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE, D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : d3dkmdt.h
req.include-header : D3dkmdt.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE
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
req.typenames : D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE
---

# _D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE Enumeration
The D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE enumeration indicates the pivot type in a call to <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality.md">DxgkDdiEnumVidPnCofuncModality</a>.

## Syntax
````
typedef enum _D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE { 
  D3DKMDT_EPT_UNINITIALIZED  = 0,
  D3DKMDT_EPT_VIDPNSOURCE    = 1,
  D3DKMDT_EPT_VIDPNTARGET    = 2,
  D3DKMDT_EPT_SCALING        = 3,
  D3DKMDT_EPT_ROTATION       = 4,
  D3DKMDT_EPT_NOPIVOT        = 5
} D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE;
````

## Constants

<table>

<tr>
<td>D3DKMDT_EPT_NOPIVOT</td>
<td>Indicates that the enumeration has no pivot.</td>
</tr>

<tr>
<td>D3DKMDT_EPT_ROTATION</td>
<td>Indicates that the rotatation transformation is the pivot of the enumeration.</td>
</tr>

<tr>
<td>D3DKMDT_EPT_SCALING</td>
<td>Indicates that the scaling transformation is the pivot of the enumeration.</td>
</tr>

<tr>
<td>D3DKMDT_EPT_UNINITIALIZED</td>
<td>Indicates that a variable of type D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE has not yet been assigned a meaningful value.</td>
</tr>

<tr>
<td>D3DKMDT_EPT_VIDPNSOURCE</td>
<td>Indicates that a video present source is the pivot of the enumeration.</td>
</tr>

<tr>
<td>D3DKMDT_EPT_VIDPNTARGET</td>
<td>Indicates that a video present target is the pivot of the enumeration.</td>
</tr>
</table>

## Remarks

The <b>EnumPivotType</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_enumvidpncofuncmodality.md">DXGKARG_ENUMVIDPNCOFUNCMODALITY</a> structure is a D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE value.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dkmdt.h (include D3dkmdt.h) |

## See Also

<dl>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality.md">DxgkDdiEnumVidPnCofuncModality</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMDT_ENUMCOFUNCMODALITY_PIVOT_TYPE enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
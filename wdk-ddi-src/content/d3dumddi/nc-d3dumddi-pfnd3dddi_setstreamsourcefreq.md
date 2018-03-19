---
UID: NC:d3dumddi.PFND3DDDI_SETSTREAMSOURCEFREQ
title: PFND3DDDI_SETSTREAMSOURCEFREQ
author: windows-driver-content
description: The SetStreamSourceFreq function sets the frequency divisor of a stream source that is bound to a vertex buffer.
old-location: display\setstreamsourcefreq.htm
old-project: display
ms.assetid: 92cb270c-1548-4239-81cd-5b3483769fc8
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3DDDI_SETSTREAMSOURCEFREQ, SetStreamSourceFreq, SetStreamSourceFreq callback function [Display Devices], UserModeDisplayDriver_Functions_4cb72b36-4cea-424f-b7a3-149435170f24.xml, d3dumddi/SetStreamSourceFreq, display.setstreamsourcefreq
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	SetStreamSourceFreq
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_SETSTREAMSOURCEFREQ callback function
The <i>SetStreamSourceFreq</i> function sets the frequency divisor of a stream source that is bound to a vertex buffer.

## Syntax

```
PFND3DDDI_SETSTREAMSOURCEFREQ Pfnd3dddiSetstreamsourcefreq;

HRESULT Pfnd3dddiSetstreamsourcefreq(
  HANDLE hDevice,
  CONST D3DDDIARG_SETSTREAMSOURCEFREQ *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`




## Return Value

<i>SetStreamSourceFreq</i> returns S_OK or an appropriate error result if the frequency divisor for the portion of the vertex stream source is not successfully set.

## Remarks

A user-mode display driver for a device that supports vertex shader version 3.0 and later must implement vertex stream frequency division. For version 2.0 and earlier models of vertex shader (including fixed function), the vertex shader is called once for each vertex. For each call, the input vertex registers are initialized with unique vertex elements from the vertex streams. However, if the driver uses vertex stream frequency division, the vertex shader (3.0 and later) can be called to initialize applicable input registers at a less frequent rate. 

After the stream's frequency divisor is set--for example, to 2--the driver must fetch data from the stream and pass this data into applicable input vertex registers every 2 vertices. This divisor affects each element in the stream. 

The driver uses the frequency divisor to compute the vertex offset into the vertex buffer according to the following formula: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VertexOffset = ((VertexIndex / Divider) * StreamStride) + StreamOffset </pre>
</td>
</tr>
</table></span></div>
For each vertex stream that is used, if the driver receives a start-vertex value during a call to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_drawprimitive.md">DrawPrimitive</a> function, the driver also divides this start-vertex value by the frequency divisor and factors the result in the formula. This start-vertex value is provided in the <b>VStart</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_drawprimitive.md">D3DDDIARG_DRAWPRIMITIVE</a> structure. The following formula includes the start-vertex value: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VertexOffset = (StartVertex / Divider) + 
       ((VertexIndex / Divider) * StreamStride) + StreamOffset </pre>
</td>
</tr>
</table></span></div>
Note that the preceding formulas use integer division. 

The driver ignores the setting of a stream's frequency divisor either for indexed primitives or if the driver supports only a vertex shader model that is earlier than version 3.0 (including fixed function).

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_drawprimitive.md">D3DDDIARG_DRAWPRIMITIVE</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_setstreamsourcefreq.md">D3DDDIARG_SETSTREAMSOURCEFREQ</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_drawprimitive.md">DrawPrimitive</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>
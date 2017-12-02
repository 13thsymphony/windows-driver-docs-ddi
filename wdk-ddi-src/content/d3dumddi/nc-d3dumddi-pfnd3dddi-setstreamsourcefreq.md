---
UID: NC.d3dumddi.PFND3DDDI_SETSTREAMSOURCEFREQ
title: PFND3DDDI_SETSTREAMSOURCEFREQ
author: windows-driver-content
description: The SetStreamSourceFreq function sets the frequency divisor of a stream source that is bound to a vertex buffer.
old-location: display\setstreamsourcefreq.htm
old-project: display
ms.assetid: 92cb270c-1548-4239-81cd-5b3483769fc8
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGK_MIRACAST_CHUNK_INFO, DXGK_MIRACAST_CHUNK_INFO
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
req.alt-api: SetStreamSourceFreq
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
req.iface: 
---

# PFND3DDDI_SETSTREAMSOURCEFREQ callback



## -description
<p>The <i>SetStreamSourceFreq</i> function sets the frequency divisor of a stream source that is bound to a vertex buffer.</p>


## -prototype

````
PFND3DDDI_SETSTREAMSOURCEFREQ SetStreamSourceFreq;

__checkReturn HRESULT APIENTRY SetStreamSourceFreq(
  _In_       HANDLE                        hDevice,
  _In_ const D3DDDIARG_SETSTREAMSOURCEFREQ *pData
)
{ ... }
````


## -parameters
<dl>

### -param hDevice [in]

<dd>
<p> A handle to the display device (graphics context).</p>
</dd>

### -param pData [in]

<dd>
<p> A pointer to a <a href="..\d3dumddi\ns-d3dumddi--d3dddiarg-setstreamsourcefreq.md">D3DDDIARG_SETSTREAMSOURCEFREQ</a> structure that specifies how the frequency divisor for the stream source is set.</p>
</dd>
</dl>

## -returns
<p><i>SetStreamSourceFreq</i> returns S_OK or an appropriate error result if the frequency divisor for the portion of the vertex stream source is not successfully set.</p>

## -remarks
<p>A user-mode display driver for a device that supports vertex shader version 3.0 and later must implement vertex stream frequency division. For version 2.0 and earlier models of vertex shader (including fixed function), the vertex shader is called once for each vertex. For each call, the input vertex registers are initialized with unique vertex elements from the vertex streams. However, if the driver uses vertex stream frequency division, the vertex shader (3.0 and later) can be called to initialize applicable input registers at a less frequent rate. </p>

<p>After the stream's frequency divisor is set--for example, to 2--the driver must fetch data from the stream and pass this data into applicable input vertex registers every 2 vertices. This divisor affects each element in the stream. </p>

<p>The driver uses the frequency divisor to compute the vertex offset into the vertex buffer according to the following formula: </p>

<p>For each vertex stream that is used, if the driver receives a start-vertex value during a call to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-drawprimitive.md">DrawPrimitive</a> function, the driver also divides this start-vertex value by the frequency divisor and factors the result in the formula. This start-vertex value is provided in the <b>VStart</b> member of the <a href="..\d3dumddi\ns-d3dumddi--d3dddiarg-drawprimitive.md">D3DDDIARG_DRAWPRIMITIVE</a> structure. The following formula includes the start-vertex value: </p>

<p>Note that the preceding formulas use integer division. </p>

<p>The driver ignores the setting of a stream's frequency divisor either for indexed primitives or if the driver supports only a vertex shader model that is earlier than version 3.0 (including fixed function). </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="..\d3dumddi\ns-d3dumddi--d3dddiarg-drawprimitive.md">D3DDDIARG_DRAWPRIMITIVE</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi--d3dddiarg-setstreamsourcefreq.md">D3DDDIARG_SETSTREAMSOURCEFREQ</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi--d3dddi-devicefuncs.md">D3DDDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-drawprimitive.md">DrawPrimitive</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_SETSTREAMSOURCEFREQ callback function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

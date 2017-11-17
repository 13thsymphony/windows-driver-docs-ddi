---
UID: NC.d3d10umddi.PFND3D10DDI_CREATEGEOMETRYSHADER
title: PFND3D10DDI_CREATEGEOMETRYSHADER
author: windows-driver-content
description: The CreateGeometryShader function creates a geometry shader.
old-location: display\creategeometryshader.htm
ms.assetid: b3b422e3-f8da-4aad-a230-7c7e26dd72ec
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: callback
ms.prod: windows-hardware
ms.technology: display
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CreateGeometryShader
req.alt-loc: d3d10umddi.h
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
ms.keywords: SETRESULT_INFO, SETRESULT_INFO, *PSETRESULT_INFO
req.iface: 
---

# PFND3D10DDI_CREATEGEOMETRYSHADER callback



## -description
<p>The <b>CreateGeometryShader</b> function creates a geometry shader.</p>


## -prototype

````
PFND3D10DDI_CREATEGEOMETRYSHADER CreateGeometryShader;

VOID APIENTRY CreateGeometryShader(
  _In_       D3D10DDI_HDEVICE                hDevice,
  _In_ const UINT                            *pCode,
  _In_       D3D10DDI_HSHADER                hShader,
  _In_       D3D10DDI_HRTSHADER              hRTShader,
  _In_ const D3D10DDIARG_STAGE_IO_SIGNATURES *pSignatures
)
{ ... }
````


## -parameters
<dl>

### -param <i>hDevice</i> [in]

<dd>
<p> A handle to the display device (graphics context).</p>
</dd>

### -param <i>pCode</i> [in]

<dd>
<p> An array of CONST UINT tokens that make up the shader code. The first token in the shader code stream is always the version token. The next token in the stream is the length token that determines the end of the shader code stream. For more information about the format of Direct3D version 10 shader code, see the comments inside the <i>D3d10tokenizedprogramformat.hpp</i> header file that is included with the WDK. </p>
</dd>

### -param <i>hShader</i> [in]

<dd>
<p> A handle to the driver's private data for the geometry shader. The driver returns the size, in bytes, of the memory region that the Microsoft Direct3D runtime must allocate for the private data from a call to the driver's <a href="https://msdn.microsoft.com/76cdddb0-b927-4547-ae1d-f5105905633b">CalcPrivateShaderSize</a> function. The handle is really just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its shader object. </p>
</dd>

### -param <i>hRTShader</i> [in]

<dd>
<p> A handle to the geometry shader that the driver should use anytime it calls back into the Direct3D runtime. </p>
</dd>

### -param <i>pSignatures</i> [in]

<dd>
<p> A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541746">D3D10DDIARG_STAGE_IO_SIGNATURES</a> structure that makes up the shader's signature.</p>
</dd>
</dl>

## -returns
<p>None</p>

<p>The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.</p>

## -remarks
<p>The driver can pass E_OUTOFMEMORY (if the driver runs out of memory) or D3DDDIERR_DEVICEREMOVED (if the device has been removed) in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function. The Direct3D runtime will determine that any other errors are critical. If the driver passes any errors, including D3DDDIERR_DEVICEREMOVED, the Direct3D runtime will determine that the handle is invalid; therefore, the runtime will not call the <a href="https://msdn.microsoft.com/51a3e5aa-0f17-49a6-824d-7cfe8e0a1ded">DestroyShader</a> function to destroy the handle that the <i>hShader</i> parameter specifies.</p>

<p>The driver can pass E_OUTOFMEMORY (if the driver runs out of memory) or D3DDDIERR_DEVICEREMOVED (if the device has been removed) in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function. The Direct3D runtime will determine that any other errors are critical. If the driver passes any errors, including D3DDDIERR_DEVICEREMOVED, the Direct3D runtime will determine that the handle is invalid; therefore, the runtime will not call the <a href="https://msdn.microsoft.com/51a3e5aa-0f17-49a6-824d-7cfe8e0a1ded">DestroyShader</a> function to destroy the handle that the <i>hShader</i> parameter specifies.</p>

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
<dt>D3d10umddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/76cdddb0-b927-4547-ae1d-f5105905633b">CalcPrivateShaderSize</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541746">D3D10DDIARG_STAGE_IO_SIGNATURES</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/51a3e5aa-0f17-49a6-824d-7cfe8e0a1ded">DestroyShader</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_CREATEGEOMETRYSHADER callback function%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

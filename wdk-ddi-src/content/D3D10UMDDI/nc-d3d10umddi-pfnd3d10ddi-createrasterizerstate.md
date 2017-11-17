---
UID: NC.d3d10umddi.PFND3D10DDI_CREATERASTERIZERSTATE
title: PFND3D10DDI_CREATERASTERIZERSTATE
author: windows-driver-content
description: The CreateRasterizerState function creates a rasterizer state.
old-location: display\createrasterizerstate.htm
ms.assetid: 4507b92e-2437-4f90-b527-e06773ca1e08
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
req.alt-api: CreateRasterizerState
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

# PFND3D10DDI_CREATERASTERIZERSTATE callback



## -description
<p>The <b>CreateRasterizerState</b> function creates a rasterizer state.</p>


## -prototype

````
PFND3D10DDI_CREATERASTERIZERSTATE CreateRasterizerState;

VOID APIENTRY CreateRasterizerState(
  _In_       D3D10DDI_HDEVICE            hDevice,
  _In_ const D3D10_DDI_RASTERIZER_DESC   *pRasterizerDesc,
  _In_       D3D10DDI_HRASTERIZERSTATE   hRasterizerState,
  _In_       D3D10DDI_HRTRASTERIZERSTATE hRTRasterizerState
)
{ ... }
````


## -parameters
<dl>

### -param <i>hDevice</i> [in]

<dd>
<p> A handle to the display device (graphics context).</p>
</dd>

### -param <i>pRasterizerDesc</i> [in]

<dd>
<p> A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541988">D3D10_DDI_RASTERIZER_DESC</a> structure that describes the parameters that the user-mode display driver uses to create a rasterizer state. </p>
</dd>

### -param <i>hRasterizerState</i> [in]

<dd>
<p> A handle to the driver's private data for the rasterizer state. The driver returns the size, in bytes, of the memory region that the Microsoft Direct3D runtime must allocate for the private data from a call to the driver's <a href="https://msdn.microsoft.com/8b10b2b8-21b0-451c-9a85-353222d9c288">CalcPrivateRasterizerStateSize</a> function. The handle is really just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its rasterizer state object.</p>
</dd>

### -param <i>hRTRasterizerState</i> [in]

<dd>
<p> A handle to the rasterizer state that the driver should use anytime it calls back into the Direct3D runtime. </p>
</dd>
</dl>

## -returns
<p>None</p>

<p>The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.</p>

## -remarks
<p>The driver can pass E_OUTOFMEMORY (if the driver runs out of memory) or D3DDDIERR_DEVICEREMOVED (if the device has been removed) in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function. The Direct3D runtime will determine that any other errors are critical. If the driver passes any errors, including D3DDDIERR_DEVICEREMOVED, the Direct3D runtime will determine that the handle is invalid; therefore, the runtime will not call the <a href="https://msdn.microsoft.com/7d730528-dc97-4490-a9fa-3d7916eef2e6">DestroyRasterizerState</a> function to destroy the handle that the <i>hRasterizerState</i> parameter specifies.</p>

<p>The user-mode display driver is not required to create more than 4,096 unique instances of rasterizer-state objects on a device at a time. </p>

<p>The driver can pass E_OUTOFMEMORY (if the driver runs out of memory) or D3DDDIERR_DEVICEREMOVED (if the device has been removed) in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function. The Direct3D runtime will determine that any other errors are critical. If the driver passes any errors, including D3DDDIERR_DEVICEREMOVED, the Direct3D runtime will determine that the handle is invalid; therefore, the runtime will not call the <a href="https://msdn.microsoft.com/7d730528-dc97-4490-a9fa-3d7916eef2e6">DestroyRasterizerState</a> function to destroy the handle that the <i>hRasterizerState</i> parameter specifies.</p>

<p>The user-mode display driver is not required to create more than 4,096 unique instances of rasterizer-state objects on a device at a time. </p>

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
<a href="https://msdn.microsoft.com/8b10b2b8-21b0-451c-9a85-353222d9c288">CalcPrivateRasterizerStateSize</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541988">D3D10_DDI_RASTERIZER_DESC</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/7d730528-dc97-4490-a9fa-3d7916eef2e6">DestroyRasterizerState</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_CREATERASTERIZERSTATE callback function%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

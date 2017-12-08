---
UID: NC.d3d10umddi.PFND3D11_1DDI_CREATERASTERIZERSTATE
title: PFND3D11_1DDI_CREATERASTERIZERSTATE
author: windows-driver-content
description: Creates a rasterizer state.
old-location: display\createrasterizerstate_d3d11_1_.htm
old-project: display
ms.assetid: 5640e1c9-6a38-4eca-9048-0bc9ff66c43c
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _SETRESULT_INFO, SETRESULT_INFO, *PSETRESULT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CreateRasterizerState(D3D11_1)
req.alt-loc: D3d10umddi.h
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
---

# PFND3D11_1DDI_CREATERASTERIZERSTATE callback



## -description
Creates a rasterizer state.


## -prototype

````
PFND3D11_1DDI_CREATERASTERIZERSTATE CreateRasterizerState(D3D11_1);

VOID APIENTRY* CreateRasterizerState(D3D11_1)(
             D3D10DDI_HDEVICE            hDevice,
  _In_ const D3D11_1_DDI_RASTERIZER_DESC *pRasterizerDesc,
             D3D10DDI_HRASTERIZERSTATE   hRasterizerState,
             D3D10DDI_HRTRASTERIZERSTATE hRTRasterizerState
)
{ ... }
````


## -parameters

### -param hDevice 

A handle to the display device (graphics context).

### -param pRasterizerDesc [in]

A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1_ddi_rasterizer_desc.md">D3D11_1_DDI_RASTERIZER_DESC</a> structure that describes the parameters that the user-mode display driver uses to create a rasterizer state.

### -param hRasterizerState 

A handle to the driver's private data for the rasterizer state. The driver returns the size, in bytes, of the memory region that the Direct3D runtime must allocate for the private data from a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivaterasterizerstatesize.md">CalcPrivateRasterizerStateSize(D3D11_1)</a> function. The handle is really just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its rasterizer state object.

### -param hRTRasterizerState 

A handle to the rasterizer state that the driver should use when it calls back into the Direct3D runtime.

## -returns
The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.

## -remarks
The driver can pass E_OUTOFMEMORY (if the driver runs out of memory) or D3DDDIERR_DEVICEREMOVED (if the device has been removed) in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function. The Direct3D runtime will determine that any other errors are critical. If the driver passes any errors, including D3DDDIERR_DEVICEREMOVED, the Direct3D runtime will determine that the handle is incorrect; therefore, the runtime will not call the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyrasterizerstate.md">DestroyRasterizerState</a> function to destroy the handle that the <i>hRasterizerState</i> parameter specifies.

The user-mode display driver is not required to create more than 4,096 unique instances of rasterizer-state objects on a device at a time. 

## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client
</th>
<td width="70%">
Windows 8
</td>
</tr>
<tr>
<th width="30%">
Minimum supported server
</th>
<td width="70%">
Windows Server 2012
</td>
</tr>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header
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
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivaterasterizerstatesize.md">CalcPrivateRasterizerStateSize(D3D11_1)</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1_ddi_rasterizer_desc.md">D3D11_1_DDI_RASTERIZER_DESC</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyrasterizerstate.md">DestroyRasterizerState</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_CREATERASTERIZERSTATE callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

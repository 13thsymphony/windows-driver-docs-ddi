---
UID: NC.d3d10umddi.PFND3D10_1DDI_CREATEBLENDSTATE
title: PFND3D10_1DDI_CREATEBLENDSTATE
author: windows-driver-content
description: The CreateBlendState(D3D10_1) function creates a blend state.
old-location: display\createblendstate_d3d10_1_.htm
old-project: display
ms.assetid: 1b258f28-c386-477c-92d1-cb5918080dcf
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _SETRESULT_INFO, SETRESULT_INFO, *PSETRESULT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CreateBlendState(D3D10_1) is supported on Windows Vista with Service Pack 1 (SP1) and later versions and Windows Server 2008 and later versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CreateBlendState_d3d10_1_
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
---

# PFND3D10_1DDI_CREATEBLENDSTATE callback



## -description
The <b>CreateBlendState(D3D10_1)</b> function creates a blend state.


## -prototype

````
PFND3D10_1DDI_CREATEBLENDSTATE CreateBlendState_d3d10_1_;

VOID APIENTRY CreateBlendState_d3d10_1_(
  _In_       D3D10DDI_HDEVICE       hDevice,
  _In_ const D3D10_1_DDI_BLEND_DESC *pBlendDesc,
  _In_       D3D10DDI_HBLENDSTATE   hBlendState,
  _In_       D3D10DDI_HRTBLENDSTATE hRTBlendState
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).

### -param pBlendDesc [in]

 A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10_1_ddi_blend_desc.md">D3D10_1_DDI_BLEND_DESC</a> structure that describes the parameters that the user-mode display driver uses to create a blend state. 

### -param hBlendState [in]

 A handle to the driver's private data for the blend state. The driver returns the size, in bytes, of the memory region that the Microsoft Direct3D runtime must allocate for the private data from a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_1ddi_calcprivateblendstatesize.md">CalcPrivateBlendStateSize(D3D10_1)</a> function. The handle is really just a pointer to a region of memory, the size of which the driver requested. The driver uses this region of memory to store internal data structures that are related to its blend state object. 

### -param hRTBlendState [in]

 A handle to the blend state that the driver should use anytime it calls back into the Direct3D runtime. 

## -returns
None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the Remarks section.

## -remarks
The driver can pass E_OUTOFMEMORY (if the driver runs out of memory) or D3DDDIERR_DEVICEREMOVED (if the device has been removed) in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> function. The Direct3D runtime will determine that any other errors are critical. If the driver passes any errors, including D3DDDIERR_DEVICEREMOVED, the Direct3D runtime will determine that the handle is invalid; therefore, the runtime will not call the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_destroyblendstate.md">DestroyBlendState</a> function to destroy the handle that the <i>hBlendState</i> parameter specifies.

The user-mode display driver is not required to create more than 4,096 unique instances of blend-state objects on a device at one time. 

## -requirements
<table>
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
Version
</th>
<td width="70%">
<i>CreateBlendState(D3D10_1)</i> is supported on Windows Vista with Service Pack 1 (SP1) and later versions and Windows Server 2008 and later versions. 
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
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_1ddi_calcprivateblendstatesize.md">CalcPrivateBlendStateSize(D3D10_1)</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d10_1ddi_devicefuncs.md">D3D10_1DDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d10_1_ddi_blend_desc.md">D3D10_1_DDI_BLEND_DESC</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10_1DDI_CREATEBLENDSTATE callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

---
UID: NC.d3d10umddi.PFND3D10DDI_STATE_IA_INPUTLAYOUT_CB
title: PFND3D10DDI_STATE_IA_INPUTLAYOUT_CB
author: windows-driver-content
description: The pfnStateIaInputLayoutCb function causes the Microsoft Direct3D 10 runtime to refresh the input layout state.
old-location: display\pfnstateiainputlayoutcb.htm
old-project: display
ms.assetid: fce49c60-8573-4a28-9d1c-5cf33d260db3
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: SETRESULT_INFO, SETRESULT_INFO, *PSETRESULT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: pfnStateIaInputLayoutCb
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
req.iface: 
---

# PFND3D10DDI_STATE_IA_INPUTLAYOUT_CB callback



## -description
<p>The <b>pfnStateIaInputLayoutCb</b> function causes the Microsoft Direct3D 10 runtime to refresh the input layout state.</p>


## -prototype

````
PFND3D10DDI_STATE_IA_INPUTLAYOUT_CB pfnStateIaInputLayoutCb;

void APIENTRY pfnStateIaInputLayoutCb(
  _In_ D3D10DDI_HRTCORELAYER hRuntimeDevice
)
{ ... }
````


## -parameters
<dl>

### -param <i>hRuntimeDevice</i> [in]

<dd>
<p> A handle to a context for the core Direct3D 10 runtime. This handle is supplied to the driver in a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-createdevice.md">CreateDevice(D3D10)</a> function. </p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks


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
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-createdevice.md">CreateDevice(D3D10)</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi-corelayer-devicecallbacks.md">D3D10DDI_CORELAYER_DEVICECALLBACKS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_STATE_IA_INPUTLAYOUT_CB callback function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

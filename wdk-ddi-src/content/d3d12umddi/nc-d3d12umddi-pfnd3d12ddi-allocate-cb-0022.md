---
UID: NC.d3d12umddi.PFND3D12DDI_ALLOCATE_CB_0022
title: PFND3D12DDI_ALLOCATE_CB_0022
author: windows-driver-content
description: The pfnAllocateCb callback function controls heap allocation by using a D3D12DDICB_ALLOCATE_0022 value.
old-location: display\pfnd3d12ddi_allocate_cb_0022.htm
old-project: display
ms.assetid: D0326C98-F187-4F62-AE60-60F0B38AB0D4
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DWDDM2_2DDI_SWIZZLE_PATTERN_DESC, D3DWDDM2_2DDI_SWIZZLE_PATTERN_DESC
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: pfnAllocateCb
req.alt-loc: D3d12umddi.h
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

# PFND3D12DDI_ALLOCATE_CB_0022 callback



## -description
<p>The <i>pfnAllocateCb</i> callback function controls heap allocation by using a <a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddicb-allocate-0022.md">D3D12DDICB_ALLOCATE_0022</a> value.</p>


## -prototype

````
PFND3D12DDI_ALLOCATE_CB_0022 pfnAllocateCb;

HRESULT APIENTRY CALLBACK* pfnAllocateCb(
  _In_    D3D12DDI_HRTDEVICE       hRTDevice,
  _Inout_ D3D12DDICB_ALLOCATE_0022 *Allocate
)
{ ... }
````


## -parameters
<dl>

### -param <i>hRTDevice</i> [in]

<dd>
<p>The handle for a device.</p>
</dd>

### -param <i>Allocate</i> [in, out]

<dd>
<p>A <a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddicb-allocate-0022.md">D3D12DDICB_ALLOCATE_0022</a> structure that contains information for an allocation.</p>
</dd>
</dl>

## -returns
<p>If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.</p>

## -remarks
<p>Access this callback function by using the <a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi-corelayer-devicecallbacks-0022~r1.md">D3D12DDI_CORELAYER_DEVICECALLBACKS_0022</a> structure.</p>

<p>The driver must check the return value of the function.</p>

<p>Access this callback function by using the <a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi-corelayer-devicecallbacks-0022~r1.md">D3D12DDI_CORELAYER_DEVICECALLBACKS_0022</a> structure.</p>

<p>The driver must check the return value of the function.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3d12umddi.h (include D3d12umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi-corelayer-devicecallbacks-0022~r1.md">D3D12DDI_CORELAYER_DEVICECALLBACKS_0022</a>
</dt>
<dt>
<a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddicb-allocate-0022.md">D3D12DDICB_ALLOCATE_0022</a>
</dt>
<dt>
<a href="..\d3d12umddi\nc-d3d12umddi-pfnd3d12ddi-deallocate-cb-0022.md">pfnDeallocateCb</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D12DDI_ALLOCATE_CB_0022 callback function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

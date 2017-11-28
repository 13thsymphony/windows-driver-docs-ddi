---
UID: NC.d3dhal.LPD3DHAL_CONTEXTDESTROYCB
title: LPD3DHAL_CONTEXTDESTROYCB
author: windows-driver-content
description: The D3dContextDestroy function deletes the specified context.
old-location: display\d3dcontextdestroy.htm
old-project: display
ms.assetid: caed780c-06a1-4697-b102-bffb134ecf84
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DTRANSFORMCAPS, D3DTRANSFORMCAPS, *LPD3DTRANSFORMCAPS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3dContextDestroy
req.alt-loc: d3dhal.h
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

# LPD3DHAL_CONTEXTDESTROYCB callback



## -description
<p>The <b>D3dContextDestroy</b> function deletes the specified context.</p>


## -prototype

````
LPD3DHAL_CONTEXTDESTROYCB D3dContextDestroy;

DWORD APIENTRY D3dContextDestroy(
  _In_ LPD3DHAL_CONTEXTDESTROYDATA pcdd
)
{ ... }
````


## -parameters
<dl>

### -param <i>pcdd</i> [in]

<dd>
<p>Points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544748">D3DHAL_CONTEXTDESTROYDATA</a> structure that contains the information required for the driver to destroy the context. </p>
</dd>
</dl>

## -returns
<p><b>D3dContextDestroy</b> returns one of the following callback codes:</p><dl>
<dt>
<a href="https://msdn.microsoft.com/da4cc7d7-6826-48aa-96c6-004e31fc3e3e">DDHAL_DRIVER_HANDLED</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/da4cc7d7-6826-48aa-96c6-004e31fc3e3e">DDHAL_DRIVER_NOTHANDLED</a>
</dt>
</dl>

## -remarks
<p>All Microsoft Direct3D drivers must support <b>D3dContextDestroy</b>.</p>

<p>The driver should free all resources it allocated to the context that is being deleted. For example, the driver should free the following resources it associated with the context: </p>

<p>Texture resources</p>

<p>Vertex and pixel <a href="https://msdn.microsoft.com/23b38ffb-ce15-4e61-bf7f-7f71848e077f">shaders</a>
</p>

<p>
<a href="https://msdn.microsoft.com/6da26a8f-553b-4995-9dda-66a7fd6d478b">Declarations and code for vertex shaders</a>
</p>

<p>Resources for <a href="https://msdn.microsoft.com/fe7dff3b-8941-4ab1-9539-0be9b59af5e6">asynchronous queries</a>
</p>

<p>The driver should not free the Microsoft DirectDraw surfaces associated with the context because these will be freed by DirectDraw in response to an application or Direct3D runtime request.</p>

<p>If the driver cached the pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550595">DD_DIRECTDRAW_LOCAL</a> structure that was passed in as the <b>lpDDLcl</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544739">D3DHAL_CONTEXTCREATEDATA</a> structure when <a href="..\d3dhal\nc-d3dhal-lpd3dhal-contextcreatecb.md">D3dContextCreate</a> was called, the pointer might become invalid before <b>D3dContextDestroy</b> is called. Therefore, <b>D3dContextDestroy</b> must not dereference this DD_DIRECTDRAW_LOCAL pointer because an access violation might result or random data might be returned. For example, if the driver's <a href="display.d3ddestroyddlocal">D3dDestroyDDLocal</a> function is called before <b>D3dContextDestroy</b>, the operating system releases this DD_DIRECTDRAW_LOCAL pointer before the <b>D3dContextDestroy</b> call.</p>

<p><b>D3dContextDestroy</b> can be called with a disabled <a href="wdkgloss.p#wdkgloss.pdev#wdkgloss.pdev"><i>PDEV</i></a>. A PDEV is disabled or enabled by calling the display driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556178">DrvAssertMode</a> function. See <a href="https://msdn.microsoft.com/f7badbe8-b24f-438a-8937-95bb98de6310">Managing PDEVs</a> for more information. </p>

<p>All Microsoft Direct3D drivers must support <b>D3dContextDestroy</b>.</p>

<p>The driver should free all resources it allocated to the context that is being deleted. For example, the driver should free the following resources it associated with the context: </p>

<p>Texture resources</p>

<p>Vertex and pixel <a href="https://msdn.microsoft.com/23b38ffb-ce15-4e61-bf7f-7f71848e077f">shaders</a>
</p>

<p>
<a href="https://msdn.microsoft.com/6da26a8f-553b-4995-9dda-66a7fd6d478b">Declarations and code for vertex shaders</a>
</p>

<p>Resources for <a href="https://msdn.microsoft.com/fe7dff3b-8941-4ab1-9539-0be9b59af5e6">asynchronous queries</a>
</p>

<p>The driver should not free the Microsoft DirectDraw surfaces associated with the context because these will be freed by DirectDraw in response to an application or Direct3D runtime request.</p>

<p>If the driver cached the pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550595">DD_DIRECTDRAW_LOCAL</a> structure that was passed in as the <b>lpDDLcl</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544739">D3DHAL_CONTEXTCREATEDATA</a> structure when <a href="..\d3dhal\nc-d3dhal-lpd3dhal-contextcreatecb.md">D3dContextCreate</a> was called, the pointer might become invalid before <b>D3dContextDestroy</b> is called. Therefore, <b>D3dContextDestroy</b> must not dereference this DD_DIRECTDRAW_LOCAL pointer because an access violation might result or random data might be returned. For example, if the driver's <a href="display.d3ddestroyddlocal">D3dDestroyDDLocal</a> function is called before <b>D3dContextDestroy</b>, the operating system releases this DD_DIRECTDRAW_LOCAL pointer before the <b>D3dContextDestroy</b> call.</p>

<p><b>D3dContextDestroy</b> can be called with a disabled <a href="wdkgloss.p#wdkgloss.pdev#wdkgloss.pdev"><i>PDEV</i></a>. A PDEV is disabled or enabled by calling the display driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556178">DrvAssertMode</a> function. See <a href="https://msdn.microsoft.com/f7badbe8-b24f-438a-8937-95bb98de6310">Managing PDEVs</a> for more information. </p>

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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dhal.h (include D3dhal.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dhal\nc-d3dhal-lpd3dhal-contextcreatecb.md">D3dContextCreate</a>
</dt>
<dt>
<a href="display.d3ddestroyddlocal">D3dDestroyDDLocal</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544739">D3DHAL_CONTEXTCREATEDATA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544748">D3DHAL_CONTEXTDESTROYDATA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550595">DD_DIRECTDRAW_LOCAL</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20LPD3DHAL_CONTEXTDESTROYCB callback function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

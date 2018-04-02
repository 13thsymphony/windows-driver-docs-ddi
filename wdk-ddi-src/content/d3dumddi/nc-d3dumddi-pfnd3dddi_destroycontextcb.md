---
UID: NC:d3dumddi.PFND3DDDI_DESTROYCONTEXTCB
title: PFND3DDDI_DESTROYCONTEXTCB
author: windows-driver-content
description: The pfnDestroyContextCb function destroys the context that was created through a call to the pfnCreateContextCb function.
old-location: display\pfndestroycontextcb.htm
old-project: display
ms.assetid: 6b65d75b-544b-4153-b821-d59d6f85673d
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3Druntime_Functions_61661c25-9c5c-4ca1-8015-a32ed840fd0a.xml, PFND3DDDI_DESTROYCONTEXTCB, d3dumddi/pfnDestroyContextCb, display.pfndestroycontextcb, pfnDestroyContextCb, pfnDestroyContextCb callback function [Display Devices]
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
-	pfnDestroyContextCb
product:
- Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_DESTROYCONTEXTCB callback function
The <b>pfnDestroyContextCb</b> function destroys the context that was created through a call to the <a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a> function.

## Syntax

```
PFND3DDDI_DESTROYCONTEXTCB Pfnd3dddiDestroycontextcb;

HRESULT Pfnd3dddiDestroycontextcb(
  HANDLE hDevice,
  CONST D3DDDICB_DESTROYCONTEXT *
)
{...}
```

## Parameters

`hDevice`

A handle to a display device (that is, the graphics context).

`*`




## Return Value

<b>pfnDestroyContextCb</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The context was successfully destroyed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect.

</td>
</tr>
</table>
 

This function might also return other HRESULT values.

## Remarks

If the specified context has not finished the work that is currently queued to it, the <b>pfnDestroyContextCb</b> function blocks until the context finishes its work and then returns. 

<b>pfnDestroyContextCb</b> returns an error if the context to destroy currently owns a synchronization object.

<b>Direct3D Version 11 Note:  </b>For more information about how the driver calls <b>pfnDestroyContextCb</b>, see <a href="https://msdn.microsoft.com/014a5e44-f8c4-45c0-96e8-d82f37b8b28d">Changes from Direct3D 10</a>.

The following code example shows how to destroy the default context for a display device.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>    if (m_d3dCallbacks.pfnDestroyContextCb) {
        D3DDDICB_DESTROYCONTEXT DestroyContext;
        DestroyContext.hContext = m_sContexts[MULTI_ENGINE_NODE_3D].hContext;
        m_d3dCallbacks.pfnDestroyContextCb(m_hD3D, &amp;DestroyContext);
        m_sContexts[MULTI_ENGINE_NODE_3D].hContext = NULL;
    }</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544169">D3DDDICB_DESTROYCONTEXT</a>



<a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a>
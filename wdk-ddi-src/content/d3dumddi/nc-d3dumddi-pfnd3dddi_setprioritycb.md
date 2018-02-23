---
UID: NC:d3dumddi.PFND3DDDI_SETPRIORITYCB
title: PFND3DDDI_SETPRIORITYCB
author: windows-driver-content
description: The pfnSetPriorityCb function sets the priority level of a resource or list of allocations.
old-location: display\pfnsetprioritycb.htm
old-project: display
ms.assetid: 1812cb0f-9232-4813-9c7b-74c9fa4d03cf
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.pfnsetprioritycb, pfnSetPriorityCb callback function [Display Devices], pfnSetPriorityCb, PFND3DDDI_SETPRIORITYCB, PFND3DDDI_SETPRIORITYCB, d3dumddi/pfnSetPriorityCb, D3Druntime_Functions_4bd6f90d-e958-43cc-8267-36d4d0448096.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dumddi.h
apiname:
-	pfnSetPriorityCb
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_SETPRIORITYCB callback function
The <i>pfnSetPriorityCb</i> function sets the priority level of a resource or list of allocations.

## Syntax

```
PFND3DDDI_SETPRIORITYCB Pfnd3dddiSetprioritycb;

HRESULT Pfnd3dddiSetprioritycb(
  HANDLE hDevice,
  D3DDDICB_SETPRIORITY *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`




## Return Value

<i>pfnSetPriorityCb</i> returns one of the following values:

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
The priority level was successfully set.

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

The user-mode display driver can call the <i>pfnSetPriorityCb</i> function to set the priority of the underlying resource or list of allocations. If the priority level of a resource is set, all of the allocations that belong to the resource are set to the specified priority level. Typically, the user-mode display driver sets the priority of a resource or list of allocations after the Microsoft Direct3D runtime calls the user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setpriority.md">SetPriority</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff569657">SetResourcePriorityDXGI</a> function to set the eviction-from-memory priority for a resource. However, the user-mode display driver can set the priority of allocations at any time. 

After an application requests to set the priority level of a surface, the user-mode display driver should set the appropriate resource or list of allocations to the priority level that is specified by the application. 

<div class="alert"><b>Note</b>    Priority levels are only a hint to the video memory manager; they can be ignored by the memory manager under various conditions. </div>
<div> </div>
An allocation priority defines both the likelihood that the allocation remains resident and the likelihood of how hard the video memory manager will try to respect the driver's preference for the placement of the allocation. The following priority levels are defined in the D3dukmdt.h header file:



The driver can use priority levels other than the preceding defined values when appropriate. For example, marking an allocation with a priority level of 0x78000001 indicates that the allocation is slightly above normal. 


#### Examples

The following code example shows how to set priority level.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HRESULT CD3DContext::SetPriority(CONST D3DDDIARG_SETPRIORITY* pSetPriority) {
    DWORD  dwSurfaceHandle = (DWORD)(DWORD_PTR)pSetPriority-&gt;hResource;
    CResource   &amp;res = m_RTbl[dwSurfaceHandle];
    D3DDDICB_SETPRIORITY    setPri;
    UINT                    priority;

    priority = pSetPriority-&gt;Priority;

    memset(&amp;setPri, 0, sizeof(setPri));

    setPri.hResource   = res.m_hResRuntime;
    setPri.pPriorities = &amp;priority;

    return (m_d3dCallbacks.pfnSetPriorityCb(m_hD3D, &amp;setPri));
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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569657">SetResourcePriorityDXGI</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_setpriority.md">D3DDDICB_SETPRIORITY</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_setpriority.md">D3DDDICB_SETPRIORITY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569657">SetResourcePriorityDXGI</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setpriority.md">SetPriority</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_SETPRIORITYCB callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
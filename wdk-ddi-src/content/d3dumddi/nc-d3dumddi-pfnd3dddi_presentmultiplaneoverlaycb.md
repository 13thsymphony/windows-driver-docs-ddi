---
UID : NC:d3dumddi.PFND3DDDI_PRESENTMULTIPLANEOVERLAYCB
title : PFND3DDDI_PRESENTMULTIPLANEOVERLAYCB
author : windows-driver-content
description : Copies content from a source multiplane overlay allocation to a destination allocation. Can be called by Windows Display Driver Model (WDDM) 1.3 or later user-mode display drivers.
old-location : display\pfnpresentmultiplaneoverlaycb_d3d.htm
old-project : display
ms.assetid : f355c29a-8a8d-46aa-b3b3-c93c0afef266
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.pfnpresentmultiplaneoverlaycb_d3d, pfnPresentMultiPlaneOverlayCb callback function [Display Devices], pfnPresentMultiPlaneOverlayCb, PFND3DDDI_PRESENTMULTIPLANEOVERLAYCB, PFND3DDDI_PRESENTMULTIPLANEOVERLAYCB, d3dumddi/pfnPresentMultiPlaneOverlayCb
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : d3dumddi.h
req.include-header : D3dumddi.h
req.target-type : Desktop
req.target-min-winverclnt : Windows 8.1
req.target-min-winversvr : Windows Server 2012 R2
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : DXGK_PTE
---


# PFND3DDDI_PRESENTMULTIPLANEOVERLAYCB callback function
Copies content from a source multiplane overlay allocation to a destination allocation. Can be called by Windows Display Driver Model (WDDM) 1.3 or later user-mode display drivers.

## Syntax

```
PFND3DDDI_PRESENTMULTIPLANEOVERLAYCB Pfnd3dddiPresentmultiplaneoverlaycb;

HRESULT Pfnd3dddiPresentmultiplaneoverlaycb(
  HANDLE hDevice,
  CONST D3DDDICB_PRESENTMULTIPLANEOVERLAY *
)
{...}
```

## Parameters

`hDevice`

A handle to a display device (graphics context).

`*`




## Return Value

Returns one of these values:
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
Content was successfully copied.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

        The function could not complete because of insufficient memory.

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

## Remarks

The user-mode display driver should call this function only after it has successfully processed a call by the Microsoft DirectX Graphics Infrastructure (DXGI) runtime to the <a href="https://msdn.microsoft.com/3AC47977-A5F3-44A6-8F89-A1EA5E0BB6E4">pfnPresentMultiplaneOverlay (D3D)</a> function.
<div class="alert"><b>Note</b>  When the display driver calls <b>pfnPresentMultiPlaneOverlayCb (D3D)</b>, it must maintain the same order of allocations in the <b>AllocationInfo</b> array member of the  <a href="..\d3dumddi\ns-d3dumddi-d3dddicb_presentmultiplaneoverlay.md">D3DDDICB_PRESENTMULTIPLANEOVERLAY</a> structure as it received from the Microsoft Direct3D runtime when the runtime called <a href="https://msdn.microsoft.com/3AC47977-A5F3-44A6-8F89-A1EA5E0BB6E4">pfnPresentMultiplaneOverlay (D3D)</a>.<p class="note">For example, the allocation handle in index 1 of <b>AllocationInfo</b> must represent the same resource that was passed to the driver in index 1 of the <i>pPresentPlanes</i> member of the <a href="..\d3dumddi\ns-d3dumddi-d3dddiarg_presentmultiplaneoverlay.md">D3DDDIARG_PRESENTMULTIPLANEOVERLAY</a> structure used with <a href="https://msdn.microsoft.com/3AC47977-A5F3-44A6-8F89-A1EA5E0BB6E4">pfnPresentMultiplaneOverlay (D3D)</a>.

</div><div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows 8.1 |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/3AC47977-A5F3-44A6-8F89-A1EA5E0BB6E4">pfnPresentMultiplaneOverlay (D3D)</a>

<a href="..\d3dumddi\ns-d3dumddi-d3dddicb_presentmultiplaneoverlay.md">D3DDDICB_PRESENTMULTIPLANEOVERLAY</a>

<a href="..\d3dumddi\ns-d3dumddi-d3dddiarg_presentmultiplaneoverlay.md">D3DDDIARG_PRESENTMULTIPLANEOVERLAY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20pfnPresentMultiPlaneOverlayCb (D3D) callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
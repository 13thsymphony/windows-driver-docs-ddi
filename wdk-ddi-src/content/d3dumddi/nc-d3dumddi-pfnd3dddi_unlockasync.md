---
UID : NC:d3dumddi.PFND3DDDI_UNLOCKASYNC
title : PFND3DDDI_UNLOCKASYNC
author : windows-driver-content
description : The UnlockAsync function unlocks a resource or a surface within the resource that the LockAsync function previously locked.
old-location : display\unlockasync.htm
old-project : display
ms.assetid : 6af04c22-e559-4328-a20a-034b443fddc6
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _DXGK_PTE, DXGK_PTE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : d3dumddi.h
req.include-header : D3dumddi.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : UnlockAsync
req.alt-loc : d3dumddi.h
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
req.typenames : DXGK_PTE
---


# PFND3DDDI_UNLOCKASYNC callback function
The <i>UnlockAsync</i> function unlocks a resource or a surface within the resource that the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockasync.md">LockAsync</a> function previously locked.

## Syntax

```
PFND3DDDI_UNLOCKASYNC Pfnd3dddiUnlockasync;

HRESULT Pfnd3dddiUnlockasync(
  HANDLE hDevice,
  CONST D3DDDIARG_UNLOCKASYNC *
)
{...}
```

## Parameters

`hDevice`

A handle to a display device (that is, the graphics context).

`*`




## Return Value

<i>UnlockAsync</i> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The resource is successfully unlocked.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl><i>UnlockAsync</i> could not allocate the required memory for it to complete.
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>The resource that <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_unlockasync.md">D3DDDIARG_UNLOCKASYNC</a> describes was not locked by a previous call to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockasync.md">LockAsync</a> function.

## Remarks

A user-mode display driver should call the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_unlockcb.md">pfnUnlockCb</a> function with the appropriate allocation handle after the <i>UnlockAsync</i> function is called. 

A user-mode display driver optionally implements <i>UnlockAsync</i>; the Microsoft Direct3D runtime calls <i>UnlockAsync</i> only if the driver implements the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockasync.md">LockAsync</a>, <i>UnlockAsync</i>, and <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_rename.md">Rename</a> functions. 

Like <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockasync.md">LockAsync</a>, <i>UnlockAsync</i> is called on the main application thread while most other calls to the user-mode display driver functions are made on a worker thread (on multiple-processor computers). 

If a user-mode display driver exposes a DDI version of 0x0000000B or greater (the driver returns this value in the <b>DriverVersion</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_openadapter.md">D3D10DDIARG_OPENADAPTER</a> structure in a call to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_openadapter.md">OpenAdapter</a> function), the Direct3D runtime will call <i>UnlockAsync</i> in a reentrant manner. When the runtime calls <i>UnlockAsync</i> in a reentrant manner, one thread can execute inside <i>UnlockAsync</i> while another thread that references the same display device executes inside of another user-mode display driver function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dumddi.h (include D3dumddi.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_unlockasync.md">D3DDDIARG_UNLOCKASYNC</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockasync.md">LockAsync</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_unlockcb.md">pfnUnlockCb</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_rename.md">Rename</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_UNLOCKASYNC callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
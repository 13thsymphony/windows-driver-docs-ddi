---
UID : NC:d3dumddi.PFND3DDDI_SETASYNCCALLBACKSCB
title : PFND3DDDI_SETASYNCCALLBACKSCB
author : windows-driver-content
description : The pfnSetAsyncCallbacksCb function notifies the Microsoft Direct3D runtime whether the runtime will start or stop receiving calls to the runtime's callback functions from a worker thread.
old-location : display\pfnsetasynccallbackscb.htm
old-project : display
ms.assetid : 7f046e5a-e8a2-4e39-ae31-d37afc03f21f
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
req.alt-api : pfnSetAsyncCallbacksCb
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


# PFND3DDDI_SETASYNCCALLBACKSCB callback function
The <b>pfnSetAsyncCallbacksCb</b> function notifies the Microsoft Direct3D runtime whether the runtime will start or stop receiving calls to the runtime's callback functions from a worker thread.

## Syntax

```
PFND3DDDI_SETASYNCCALLBACKSCB Pfnd3dddiSetasynccallbackscb;

HRESULT Pfnd3dddiSetasynccallbackscb(
  HANDLE hDevice,
  BOOL Enable
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`Enable`

A Boolean value that specifies whether the runtime will start or stop receiving calls to the runtime's callback functions from a worker thread. <b>TRUE</b> indicates that the runtime will start receiving calls to its callback functions from a worker thread; <b>FALSE</b> indicates that the runtime will stop receiving calls to its callback functions from a worker thread.


## Return Value

<b>pfnSetAsyncCallbacksCb</b> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The Direct3D runtime was successfully notified. 
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>Parameters were validated and determined to be incorrect.

 

This function might also return other HRESULT values.

## Remarks

If a user-mode display driver implements its own multiple-processor optimizations (that is, the driver creates a worker thread and processes commands in that thread), the driver must call <b>pfnSetAsyncCallbacksCb</b> to notify the Direct3D runtime whether the runtime will start or stop receiving calls to the runtime's callback functions from the worker thread. Additionally, such drivers must not implement the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockasync.md">LockAsync</a>, <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_unlockasync.md">UnlockAsync</a>, and <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_rename.md">Rename</a> functions. This ensures that the runtime does not attempt to use its own multiple-processor optimizations. 

The user-mode display driver can call <b>pfnSetAsyncCallbacksCb</b> only on the main application thread (that is, the thread that called into the driver). The driver's worker thread cannot call <b>pfnSetAsyncCallbacksCb</b>. At any point in time, only one thread that references a particular rendering device can run in any of the runtime's callback functions. 

Before the user-mode display driver calls any of the runtime's callback functions on a thread other than the main application thread, the driver must pass <b>TRUE</b> to the <i>Enable</i> parameter in a call to <b>pfnSetAsyncCallbacksCb</b>. Before the user-mode display driver calls any of the runtime's callback functions on the main application thread, the driver must pass <b>FALSE</b> to the <i>Enable</i> parameter in a call to <b>pfnSetAsyncCallbacksCb</b>. 

Within the implementation of <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_flush.md">Flush</a> for each rendering device, the driver calls <b>pfnSetAsyncCallbacksCb</b> and passes <b>FALSE</b> to the <i>Enable</i> parameter.

When the driver passes <b>TRUE</b> to the <i>Enable</i> parameter in a call to <b>pfnSetAsyncCallbacksCb</b>, the runtime puts itself in a state where it does not immediately respond to device-lost situations in its callback functions. Instead, when the runtime detects a device lost in a callback function while in this state, it sets a bit that indicates that the event occurred. When the driver passes <b>FALSE</b> to the <i>Enable</i> parameter in a call to <b>pfnSetAsyncCallbacksCb</b>, the runtime checks the bit to determine if a device lost occurred. If the bit is set, the runtime performs its typical device-lost handling. After this point, the driver no longer receives most calls to its functions from the runtime. 

Only DirectX 9 and DirectX 9L versions of the runtime support <b>pfnSetAsyncCallbacksCb</b>. DirectX 10 and later versions of the runtime set the <b>pfnSetAsyncCallbacksCb</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicecallbacks.md">D3DDDI_DEVICECALLBACKS</a> structure to <b>NULL</b> when the runtime calls the user-mode display driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a> function to create a rendering device. 

Drivers can call the runtime's callback functions only from a worker thread if the runtime previously set the <b>pfnSetAsyncCallbacksCb</b> member of D3DDDI_DEVICECALLBACKS to non-<b>NULL</b> in a call to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createdevice.md">CreateDevice</a> function.

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
<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicecallbacks.md">D3DDDI_DEVICECALLBACKS</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createdevice.md">CreateDevice</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_flush.md">Flush</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockasync.md">LockAsync</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_rename.md">Rename</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_unlockasync.md">UnlockAsync</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_SETASYNCCALLBACKSCB callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
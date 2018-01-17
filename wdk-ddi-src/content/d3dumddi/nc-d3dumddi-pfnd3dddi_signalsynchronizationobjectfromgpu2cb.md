---
UID: NC:d3dumddi.PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2CB
title: PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2CB
author: windows-driver-content
description: pfnSignalSynchronizationObjectFromGpu2Cb is used to signal a monitored fence.
old-location: display\pfnsignalsynchronizationobjectfromgpu2cb.htm
old-project: display
ms.assetid: 03F9E47D-A3CA-44A1-A136-8236309D3D36
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_GRAPHICSPOWER_REGISTER_OUTPUT, *PDXGK_GRAPHICSPOWER_REGISTER_OUTPUT, DXGK_GRAPHICSPOWER_REGISTER_OUTPUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: pfnSignalSynchronizationObjectFromGpu2Cb
req.alt-loc: d3dumddi.h
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
req.typenames: *PDXGK_GRAPHICSPOWER_REGISTER_OUTPUT, DXGK_GRAPHICSPOWER_REGISTER_OUTPUT
---

# PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2CB callback



## -description
<b>pfnSignalSynchronizationObjectFromGpu2Cb</b> is used to signal a monitored fence. When a particular graphics processing unit (GPU) engine is not capable of writing a new monitored fence value directly using its GPU virtual address, the driver needs to flush its command buffer and issue a signal from the GPU packet using <b>pfnSignalSynchronizationObjectFromGpu2Cb</b>. For Windows Display Driver Model (WDDM) v2 drivers, existing <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectcb.md">pfnSignalSynchronizationObjectCb</a> and <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobject2cb.md">pfnSignalSynchronizationObject2Cb</a> callbacks are deprecated and will eventually be removed. WDDM v2 user mode drivers should switch to <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectfromgpucb.md">pfnSignalSynchronizationObjectFromGpuCb</a>, as it supports all synchronization object types. 



## -prototype

````
PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2CB pfnSignalSynchronizationObjectFromGpu2Cb;

HRESULT APIENTRY CALLBACK* pfnSignalSynchronizationObjectFromGpu2Cb(
  _In_       HANDLE                                       hDevice,
  _In_ const D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2 *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

A handle to the display device.


### -param pData [in]

A pointer to a <a href="..\d3dumddi\ns-d3dumddi-d3dddicb_signalsynchronizationobjectfromgpu2.md">D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2</a> structure that provides the details of the requested operation.




## -returns
If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectcb.md">pfnSignalSynchronizationObjectCb</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobject2cb.md">pfnSignalSynchronizationObject2Cb</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_signalsynchronizationobjectfromgpucb.md">pfnSignalSynchronizationObjectFromGpuCb</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-d3dddicb_signalsynchronizationobjectfromgpu2.md">D3DDDICB_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_SIGNALSYNCHRONIZATIONOBJECTFROMGPU2CB callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


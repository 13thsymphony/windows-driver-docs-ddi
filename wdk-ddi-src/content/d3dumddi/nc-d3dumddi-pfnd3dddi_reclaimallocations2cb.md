---
UID: NC:d3dumddi.PFND3DDDI_RECLAIMALLOCATIONS2CB
title: PFND3DDDI_RECLAIMALLOCATIONS2CB
author: windows-driver-content
description: pfnReclaimAllocations2Cb is called by the user mode driver to reclaim video memory allocations that were previously offered for reuse.
old-location: display\pfnreclaimallocations2cb.htm
old-project: display
ms.assetid: 1D3439BA-AB3D-4D94-B4C8-91BE9B3349A1
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
req.alt-api: pfnReclaimAllocations2Cb
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

# PFND3DDDI_RECLAIMALLOCATIONS2CB callback



## -description
<b>pfnReclaimAllocations2Cb</b> is called by the user mode driver   to reclaim video memory allocations that were previously offered  for reuse.



## -prototype

````
PFND3DDDI_RECLAIMALLOCATIONS2CB pfnReclaimAllocations2Cb;

_Check_return_ HRESULT APIENTRY CALLBACK* pfnReclaimAllocations2Cb(
  _In_    HANDLE                       hDevice,
  _Inout_ D3DDDICB_RECLAIMALLOCATIONS2 *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device.


### -param pData [in, out]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_reclaimallocations2.md">D3DDDICB_RECLAIMALLOCATIONS2</a> structure that defines the allocations to reclaim.


## -returns

      Returns one of the following values.
<dl>
<dt><b>S_OK</b></dt>
</dl>The allocations were successfully reclaimed.
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>An invalid parameter was supplied.
<dl>
<dt><b>D3DDDIERR_DEVICEREMOVED</b></dt>
</dl>The video memory manager or display miniport driver could not complete the operation because either a Plug and Play (PnP) Stop event or a Timeout Detection and Recovery (TDR) event occurred.

 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_reclaimallocations.md">D3DDDICB_RECLAIMALLOCATIONS2</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicecallbacks.md">D3DDDI_DEVICECALLBACKS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/AF3DCD16-9F8C-442A-A9A5-9EA2BD1C3B84">pfnReclaimResources</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20pfnReclaimAllocations2Cb callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


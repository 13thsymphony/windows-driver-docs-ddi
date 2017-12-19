---
UID: NS.IDDCX.IDARG_IN_SETSWAPCHAIN~R1
title: IDARG_IN_SETSWAPCHAIN
author: windows-driver-content
description: Gives information used to set the indirect swapchain.
old-location: display\idarg_in_setswapchain.htm
old-project: display
ms.assetid: 5b3a4a43-e8d4-4edf-87f3-dd3e6bb7e9dc
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: IDARG_IN_SETSWAPCHAIN,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDARG_IN_SETSWAPCHAIN
req.alt-loc: iddcx.h
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
---

# IDARG_IN_SETSWAPCHAIN structure



## -description

                 Gives information used to set the indirect swapchain.
             



## -syntax

````
typedef struct IDARG_IN_SETSWAPCHAIN {
  IDDCX_SWAPCHAIN hSwapChain;
  HANDLE          hNextSurfaceAvailable;
  LUID            RenderAdapterLuid;
} IDARG_IN_SETSWAPCHAIN, *IDARG_IN_SETSWAPCHAIN;
````


## -struct-fields

### -field hSwapChain


                     [in] Handle to indirect swapchain that will be used to pass the desktop image to the driver for processing, transmission and display.


### -field hNextSurfaceAvailable


                     [in] Handle to auto reset event that is signaled when the new image to encode is ready.


### -field RenderAdapterLuid


                     [In] LUID of the adapter where the desktop image was rendered.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Iddcx.h</dt>
</dl>
</td>
</tr>
</table>
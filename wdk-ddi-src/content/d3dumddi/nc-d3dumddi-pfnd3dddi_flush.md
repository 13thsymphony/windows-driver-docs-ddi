---
UID: NC:d3dumddi.PFND3DDDI_FLUSH
title: PFND3DDDI_FLUSH
author: windows-driver-content
description: The Flush function submits outstanding hardware commands that are in the hardware command buffer to the display miniport driver.
old-location: display\flush.htm
old-project: display
ms.assetid: 0c1a9a60-de17-41d1-b31d-c1d3c95d8121
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_GRAPHICSPOWER_REGISTER_OUTPUT, *PDXGK_GRAPHICSPOWER_REGISTER_OUTPUT, DXGK_GRAPHICSPOWER_REGISTER_OUTPUT
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
req.alt-api: Flush
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

# PFND3DDDI_FLUSH callback



## -description
The <i>Flush</i> function submits outstanding hardware commands that are in the hardware command buffer to the display miniport driver.



## -prototype

````
PFND3DDDI_FLUSH Flush;

__checkReturn HRESULT APIENTRY Flush(
  _In_ HANDLE hDevice
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).


## -returns
<i>Flush</i> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>Hardware commands were successfully flushed.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl><i>Flush</i> could not allocate the required memory for it to complete.

 


## -remarks
The Microsoft Direct3D runtime can call the user-mode display driver's <i>Flush</i> function at any time to notify the user-mode display driver to submit any outstanding hardware commands that are in the hardware command buffer to the display miniport driver. However, a call to <i>Flush</i> should never cause the user-mode display driver to submit invalid commands to the display miniport driver. 

To submit commands to the display miniport driver, the user-mode display driver's <i>Flush</i> function should typically call the runtime's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_rendercb.md">pfnRenderCb</a> function.


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_rendercb.md">pfnRenderCb</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_FLUSH callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


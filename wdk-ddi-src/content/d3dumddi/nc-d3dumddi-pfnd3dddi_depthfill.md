---
UID: NC.d3dumddi.PFND3DDDI_DEPTHFILL
title: PFND3DDDI_DEPTHFILL
author: windows-driver-content
description: The DepthFill function fills a depth buffer with a pixel value that is specified in native format.
old-location: display\depthfill.htm
old-project: display
ms.assetid: fc889cc0-d71d-4a81-8fa5-894c676ac110
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DXGK_PTE, DXGK_PTE
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
req.alt-api: DepthFill
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
---

# PFND3DDDI_DEPTHFILL callback



## -description
The <b>DepthFill</b> function fills a depth buffer with a pixel value that is specified in native format.



## -prototype

````
PFND3DDDI_DEPTHFILL DepthFill;

__checkReturn HRESULT APIENTRY DepthFill(
  _In_       HANDLE              hDevice,
  _In_ const D3DDDIARG_DEPTHFILL *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).


### -param pData [in]

 A pointer to a <a href="display.d3dddiarg_depthfill">D3DDDIARG_DEPTHFILL</a> structure that describes the parameters of the depth-fill operation.


## -returns
<b>DepthFill</b> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The depth-fill operation was successful.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_depthfill.md">DepthFill</a> could not allocate the required memory for it to complete.

 


## -remarks
DirectX version 7.0 and earlier runtimes call the <b>DepthFill</b> function to fill a depth buffer (z-buffer and stencil buffer) with a pixel value that is specified in native format.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.d3dddiarg_depthfill">D3DDDIARG_DEPTHFILL</a>
</dt>
<dt>
<a href="display.d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_DEPTHFILL callback function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


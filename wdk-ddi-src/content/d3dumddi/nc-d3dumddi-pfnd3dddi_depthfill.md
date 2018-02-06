---
UID: NC:d3dumddi.PFND3DDDI_DEPTHFILL
title: PFND3DDDI_DEPTHFILL
author: windows-driver-content
description: The DepthFill function fills a depth buffer with a pixel value that is specified in native format.
old-location: display\depthfill.htm
old-project: display
ms.assetid: fc889cc0-d71d-4a81-8fa5-894c676ac110
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.depthfill, DepthFill callback function [Display Devices], DepthFill, PFND3DDDI_DEPTHFILL, PFND3DDDI_DEPTHFILL, d3dumddi/DepthFill, UserModeDisplayDriver_Functions_4f8a5911-1ed4-439f-b629-d267161c4ea9.xml
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
-	DepthFill
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_DEPTHFILL callback function
The <b>DepthFill</b> function fills a depth buffer with a pixel value that is specified in native format.

## Syntax

```
PFND3DDDI_DEPTHFILL Pfnd3dddiDepthfill;

HRESULT Pfnd3dddiDepthfill(
  HANDLE hDevice,
  CONST D3DDDIARG_DEPTHFILL *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`




## Return Value

<b>DepthFill</b> returns one of the following values:
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
The depth-fill operation was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_depthfill.md">DepthFill</a> could not allocate the required memory for it to complete.

</td>
</tr>
</table>

## Remarks

DirectX version 7.0 and earlier runtimes call the <b>DepthFill</b> function to fill a depth buffer (z-buffer and stencil buffer) with a pixel value that is specified in native format.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_depthfill.md">D3DDDIARG_DEPTHFILL</a>

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_DEPTHFILL callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
---
UID: NC.d3dkmddi.DXGKDDI_SETDISPLAYPRIVATEDRIVERFORMAT
title: DXGKDDI_SETDISPLAYPRIVATEDRIVERFORMAT
author: windows-driver-content
description: The DxgkDdiSetDisplayPrivateDriverFormat function changes the private-format attribute of a video present source.
old-location: display\dxgkddisetdisplayprivatedriverformat.htm
old-project: display
ms.assetid: 053fdf22-20c3-4b57-94f4-0613857abfa7
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkDdiSetDisplayPrivateDriverFormat
req.alt-loc: d3dkmddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# DXGKDDI_SETDISPLAYPRIVATEDRIVERFORMAT callback



## -description
The <i>DxgkDdiSetDisplayPrivateDriverFormat</i> function changes the private-format attribute of a video present source.



## -prototype

````
DXGKDDI_SETDISPLAYPRIVATEDRIVERFORMAT DxgkDdiSetDisplayPrivateDriverFormat;

NTSTATUS APIENTRY DxgkDdiSetDisplayPrivateDriverFormat(
  _In_ const HANDLE                                hAdapter,
  _In_ const DXGKARG_SETDISPLAYPRIVATEDRIVERFORMAT *pSetDisplayPrivateDriverFormat
)
{ ... }
````


## -parameters

### -param hAdapter [in]

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.


### -param pSetDisplayPrivateDriverFormat [in]

[in] A pointer to a <a href="display.dxgkarg_setdisplayprivatedriverformat">DXGKARG_SETDISPLAYPRIVATEDRIVERFORMAT</a> structure that contains function arguments.


## -returns
<i>DxgkDdiSetDisplayPrivateDriverFormat</i> returns STATUS_SUCCESS if it succeeds; otherwise, it returns STATUS_UNSUCCESSFUL to indicate that the driver could not change the private-format attribute of the given video present source.


## -remarks
The DirectX graphics kernel subsystem calls the display miniport driver's <i>DxgkDdiSetDisplayPrivateDriverFormat</i> function after the user-mode display driver calls the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setdisplayprivatedriverformatcb.md">pfnSetDisplayPrivateDriverFormatCb</a> callback function. For example, the user-mode display driver might call <b>pfnSetDisplayPrivateDriverFormatCb</b> to change the swizzling format of the video present source when a full-screen flipping change is created. The DirectX graphics kernel subsystem then calls the display miniport driver's <i>DxgkDdiSetDisplayPrivateDriverFormat</i> to change the private-driver format of the video present source. This allows for the primary allocation to be displayed on the video present source without a need for translation of the primary surface.

<i>DxgkDdiSetDisplayPrivateDriverFormat</i> should be made pageable.


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
<dt>D3dkmddi.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.dxgkarg_setdisplayprivatedriverformat">DXGKARG_SETDISPLAYPRIVATEDRIVERFORMAT</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_setdisplayprivatedriverformatcb.md">pfnSetDisplayPrivateDriverFormatCb</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_SETDISPLAYPRIVATEDRIVERFORMAT callback function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


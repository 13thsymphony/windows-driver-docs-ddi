---
UID: NS.D3DUMDDI._D3DDDIARG_DEPTHFILL
title: _D3DDDIARG_DEPTHFILL
author: windows-driver-content
description: The D3DDDIARG_DEPTHFILL structure describes the parameters of a depth-fill operation.
old-location: display\d3dddiarg_depthfill.htm
old-project: display
ms.assetid: e4070d53-bdd6-4708-857d-7ed1e9699e21
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _D3DDDIARG_DEPTHFILL, D3DDDIARG_DEPTHFILL
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDIARG_DEPTHFILL
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

# _D3DDDIARG_DEPTHFILL structure



## -description
The D3DDDIARG_DEPTHFILL structure describes the parameters of a depth-fill operation. 


## -syntax

````
typedef struct _D3DDDIARG_DEPTHFILL {
  HANDLE hResource;
  UINT   SubResourceIndex;
  RECT   DstRect;
  UINT   Depth;
} D3DDDIARG_DEPTHFILL;
````


## -struct-fields

### -field hResource

[in] A handle to the resource.

### -field SubResourceIndex

[in] The zero-based index into the resource, which is specified by the handle in the <b>hResource</b> member. This index indicates the subresource, or buffer, on which a rectangular area is depth-filled.

### -field DstRect

[in] A <a href="display.rectl">RECTL</a> structure that indicates the upper-left and lower-right points of a rectangle on the buffer to depth fill. 

### -field Depth

A pixel value that is specified in native format for the fill depth. 

## -remarks


## -requirements
<table>
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
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_depthfill.md">DepthFill</a>
</dt>
<dt>
<a href="display.rectl">RECTL</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_DEPTHFILL structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

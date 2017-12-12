---
UID: NS.D3DUMDDI._D3DDDIARG_FLIPOVERLAY
title: _D3DDDIARG_FLIPOVERLAY
author: windows-driver-content
description: The D3DDDIARG_FLIPOVERLAY structure describes a new resource to display on a given overlay.
old-location: display\d3dddiarg_flipoverlay.htm
old-project: display
ms.assetid: 36ea4547-e9a0-49c9-8b45-903a2de60923
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _D3DDDIARG_FLIPOVERLAY, D3DDDIARG_FLIPOVERLAY
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
req.alt-api: D3DDDIARG_FLIPOVERLAY
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

# _D3DDDIARG_FLIPOVERLAY structure



## -description
The D3DDDIARG_FLIPOVERLAY structure describes a new resource to display on a given overlay. 



## -syntax

````
typedef struct _D3DDDIARG_FLIPOVERLAY {
  HANDLE                  hOverlay;
  HANDLE                  hSource;
  UINT                    SourceIndex;
  D3DDDI_FLIPOVERLAYFLAGS Flags;
} D3DDDIARG_FLIPOVERLAY;
````


## -struct-fields

### -field hOverlay

[in] A handle to the overlay hardware to be flipped. 


### -field hSource

[in] A handle to the new resource to be displayed. This resource might be the same as the resource that was previously displayed if deinterlacing interleaved data.


### -field SourceIndex

[in] The zero-based index of the subresource to be displayed.


### -field Flags

[in] A <a href="display.d3dddi_flipoverlayflags">D3DDDI_FLIPOVERLAYFLAGS</a> structure that indicates, in bit-field flags, how to flip the resource.


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
<a href="display.d3dddi_flipoverlayflags">D3DDDI_FLIPOVERLAYFLAGS</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_flipoverlay.md">FlipOverlay</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_FLIPOVERLAY structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


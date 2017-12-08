---
UID: NS.D3DUMDDI._D3DDDIARG_UPDATEOVERLAY
title: _D3DDDIARG_UPDATEOVERLAY
author: windows-driver-content
description: The D3DDDIARG_UPDATEOVERLAY structure describes an overlay to modify.
old-location: display\d3dddiarg_updateoverlay.htm
old-project: display
ms.assetid: e49f48fd-f2e8-4ccc-813f-f624e06ab365
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _D3DDDIARG_UPDATEOVERLAY, D3DDDIARG_UPDATEOVERLAY
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
req.alt-api: D3DDDIARG_UPDATEOVERLAY
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

# _D3DDDIARG_UPDATEOVERLAY structure



## -description
The D3DDDIARG_UPDATEOVERLAY structure describes an overlay to modify. 


## -syntax

````
typedef struct _D3DDDIARG_UPDATEOVERLAY {
  HANDLE             hOverlay;
  D3DDDI_OVERLAYINFO OverlayInfo;
} D3DDDIARG_UPDATEOVERLAY;
````


## -struct-fields

### -field hOverlay

[in] A handle to the overlay to modify.

### -field OverlayInfo

[in] A pointer to the <a href="display.d3dddi_overlayinfo">D3DDDI_OVERLAYINFO</a> structure that describes the modification for the overlay. 

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
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_updateoverlay.md">UpdateOverlay</a>
</dt>
<dt>
<a href="display.d3dddi_overlayinfo">D3DDDI_OVERLAYINFO</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_UPDATEOVERLAY structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

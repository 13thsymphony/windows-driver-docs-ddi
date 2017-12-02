---
UID: NS.d3dkmddi._DXGKARG_UPDATEOVERLAY
title: DXGKARG_UPDATEOVERLAY
author: windows-driver-content
description: The DXGKARG_UPDATEOVERLAY structure describes parameters for modifying an overlay.
old-location: display\dxgkarg_updateoverlay.htm
old-project: display
ms.assetid: 077f2df2-c115-4702-9472-b43df02dac42
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGKARG_UPDATEOVERLAY, DXGKARG_UPDATEOVERLAY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGKARG_UPDATEOVERLAY
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
req.iface: 
---

# DXGKARG_UPDATEOVERLAY structure



## -description
<p>The DXGKARG_UPDATEOVERLAY structure describes parameters for modifying an overlay.</p>


## -syntax

````
typedef struct _DXGKARG_UPDATEOVERLAY {
  DXGK_OVERLAYINFO OverlayInfo;
} DXGKARG_UPDATEOVERLAY;
````


## -struct-fields
<dl>

### -field OverlayInfo

<dd>
<p>[in] A <a href="..\d3dkmddi\ns-d3dkmddi--dxgk-overlayinfo.md">DXGK_OVERLAYINFO</a> structure that contains parameters that are required to modify the overlay.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi--dxgk-overlayinfo.md">DXGK_OVERLAYINFO</a>
</dt>
<dt>
<a href="display.dxgkddiupdateoverlay">DxgkDdiUpdateOverlay</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_UPDATEOVERLAY structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

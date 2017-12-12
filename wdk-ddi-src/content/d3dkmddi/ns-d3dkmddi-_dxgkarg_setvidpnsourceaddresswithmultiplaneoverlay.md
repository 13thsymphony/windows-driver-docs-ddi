---
UID: NS.D3DKMDDI._DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY
title: _DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY
author: windows-driver-content
description: Contains arguments for the DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay function.
old-location: display\dxgkarg_setvidpnsourceaddresswithmultiplaneoverlay.htm
old-project: display
ms.assetid: 12266cb0-20c1-4077-b3c5-fb902f3805d3
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY, DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY
req.alt-loc: D3dkmddi.h
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

# _DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY structure



## -description
Contains arguments for the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_setvidpnsourceaddresswithmultiplaneoverlay.md">DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay</a> function.



## -syntax

````
typedef struct _DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY {
  UINT                             ContextCount;
  HANDLE                           Context[1+D3DDDI_MAX_BROADCAST_CONTEXT];
  DXGK_SETVIDPNSOURCEADDRESS_FLAGS Flags;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID   VidPnSourceId;
  UINT                             PlaneCount;
  DXGK_MULTIPLANE_OVERLAY_PLANE    *pPlanes;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM1_3)
  UINT                             Duration;
#endif 
} DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY;
````


## -struct-fields

### -field ContextCount

[in] The number of contexts in the array that the <b>Context</b> member specifies.


### -field Context

[in] An array of handles to the contexts that contributed to a display operation.


### -field Flags

[in] A <a href="display.dxgk_setvidpnsourceaddress_flags">DXGK_SETVIDPNSOURCEADDRESS_FLAGS</a> structure that identifies the type of display operation to perform.


### -field VidPnSourceId

An integer that identifies a video present source on the display adapter.


### -field PlaneCount

The number of overlay planes that the hardware supports.




### -field pPlanes

A pointer to a <a href="display.dxgk_multiplane_overlay_plane">DXGK_MULTIPLANE_OVERLAY_PLANE</a> structure that specifies the first overlay plane to display.


### -field Duration

The length of time, in units of 100 nanoseconds, between when the current present operation flips to the screen and the next vertical blanking interrupt occurs.

If zero, the refresh rate should be the default rate based on the current mode.

Must be supported by WDDM 1.3 and later drivers. Available starting with Windows 8.1.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8.1

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012 R2

</td>
</tr>
<tr>
<th width="30%">
Header

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
<a href="display.dxgk_setvidpnsourceaddress_flags">DXGK_SETVIDPNSOURCEADDRESS_FLAGS</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_setvidpnsourceaddresswithmultiplaneoverlay.md">DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


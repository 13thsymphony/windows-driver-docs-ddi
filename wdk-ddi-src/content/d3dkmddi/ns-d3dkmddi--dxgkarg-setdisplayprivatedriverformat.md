---
UID: NS.d3dkmddi._DXGKARG_SETDISPLAYPRIVATEDRIVERFORMAT
title: DXGKARG_SETDISPLAYPRIVATEDRIVERFORMAT
author: windows-driver-content
description: The DXGKARG_SETDISPLAYPRIVATEDRIVERFORMAT structure describes how to set the private-format attribute for a video present source.
old-location: display\dxgkarg_setdisplayprivatedriverformat.htm
old-project: display
ms.assetid: a09cfc9a-26e8-4984-b5c6-7ead5aa4644e
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGKARG_SETDISPLAYPRIVATEDRIVERFORMAT, DXGKARG_SETDISPLAYPRIVATEDRIVERFORMAT
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
req.alt-api: DXGKARG_SETDISPLAYPRIVATEDRIVERFORMAT
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

# DXGKARG_SETDISPLAYPRIVATEDRIVERFORMAT structure



## -description
<p>The DXGKARG_SETDISPLAYPRIVATEDRIVERFORMAT structure describes how to set the private-format attribute for a video present source. </p>


## -syntax

````
typedef struct _DXGKARG_SETDISPLAYPRIVATEDRIVERFORMAT {
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
  HANDLE                         PrimaryAllocation;
  UINT                           PrivateDriverFormatAttribute;
} DXGKARG_SETDISPLAYPRIVATEDRIVERFORMAT;
````


## -struct-fields
<dl>

### -field VidPnSourceId

<dd>
<p>[in] The zero-based identification number that identifies the video present source in a path of a video present network (VidPN) topology to change the private driver format attribute of. </p>
</dd>

### -field PrimaryAllocation

<dd>
<p>[in] If nonzero, handle to the allocation for the current primary surface for the video present source that the <b>VidPnSourceId</b> member specifies. The display miniport driver returns this handle when its <a href="display.dxgkddicreateallocation">DxgkDdiCreateAllocation</a> function is called to create the primary surface. This handle is returned in the <b>hAllocation</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi--dxgk-allocationinfo.md">DXGK_ALLOCATIONINFO</a> structure of the primary-surface element in the <b>pAllocationInfo</b> array member of the <a href="..\d3dkmddi\ns-d3dkmddi--dxgkarg-createallocation.md">DXGKARG_CREATEALLOCATION</a> structure. This handle is a pointer to a private driver data structure that contains information about the primary allocation.</p>
<p>If <b>PrimaryAllocation</b> is set to zero, no primary surface is currently associated with the video present source. In this situation, the video present source is not visible. </p>
</dd>

### -field PrivateDriverFormatAttribute

<dd>
<p>[in] A UINT value that specifies the private-format attribute to set for the video present source that the <b>VidPnSourceId</b> member specifies.</p>
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
<a href="..\d3dkmddi\ns-d3dkmddi--dxgk-allocationinfo.md">DXGK_ALLOCATIONINFO</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi--dxgkarg-createallocation.md">DXGKARG_CREATEALLOCATION</a>
</dt>
<dt>
<a href="display.dxgkddicreateallocation">DxgkDdiCreateAllocation</a>
</dt>
<dt>
<a href="display.dxgkddisetdisplayprivatedriverformat">DxgkDdiSetDisplayPrivateDriverFormat</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_SETDISPLAYPRIVATEDRIVERFORMAT structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

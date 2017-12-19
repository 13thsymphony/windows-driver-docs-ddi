---
UID: NS.D3DKMDDI._DXGK_OVERLAYINFO
title: _DXGK_OVERLAYINFO
author: windows-driver-content
description: The DXGK_OVERLAYINFO structure describes parameters that are required to create or modify an overlay.
old-location: display\dxgk_overlayinfo.htm
old-project: display
ms.assetid: 7c2a7484-452f-4801-b650-3d8221740892
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DXGK_OVERLAYINFO, DXGK_OVERLAYINFO
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
req.alt-api: DXGK_OVERLAYINFO
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

# _DXGK_OVERLAYINFO structure



## -description
The DXGK_OVERLAYINFO structure describes parameters that are required to create or modify an overlay. 



## -syntax

````
typedef struct _DXGK_OVERLAYINFO {
  HANDLE           hAllocation;
  PHYSICAL_ADDRESS PhysicalAddress;
  UINT             SegmentId;
  RECT             DstRect;
  RECT             SrcRect;
  VOID             *pPrivateDriverData;
  UINT             PrivateDriverDataSize;
} DXGK_OVERLAYINFO;
````


## -struct-fields

### -field hAllocation

[in] A handle to the allocation to be displayed on the overlay.


### -field PhysicalAddress

[in] The physical address, within the segment that <b>SegmentId</b> specifies, of the allocation to be displayed.


### -field SegmentId

[in] The identifier of a segment in which the allocation is currently paged-in.


### -field DstRect

[in] A <a href="display.rect">RECT</a> structure that contains the overlay destination rectangle, in device coordinates.


### -field SrcRect

[in] A RECT structure that contains the overlay source rectangle, in device coordinates.


### -field pPrivateDriverData

[in] A pointer to a block of private data that is passed from the user-mode display driver to the display miniport driver. 


### -field PrivateDriverDataSize

[in] The size, in bytes, of the block of private data that <b>pPrivateDriverData</b> points to.


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
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createoverlay.md">DxgkDdiCreateOverlay</a>
</dt>
<dt>
<a href="display.dxgkarg_createoverlay">DXGKARG_CREATEOVERLAY</a>
</dt>
<dt>
<a href="display.dxgkarg_updateoverlay">DXGKARG_UPDATEOVERLAY</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_updateoverlay.md">DxgkDdiUpdateOverlay</a>
</dt>
<dt>
<a href="display.rect">RECT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_OVERLAYINFO structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


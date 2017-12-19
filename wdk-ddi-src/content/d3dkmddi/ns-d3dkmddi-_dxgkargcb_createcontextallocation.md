---
UID: NS.D3DKMDDI._DXGKARGCB_CREATECONTEXTALLOCATION
title: _DXGKARGCB_CREATECONTEXTALLOCATION
author: windows-driver-content
description: Specifies the allocation attributes of a GPU context or device-specific context.
old-location: display\dxgkargcb_createcontextallocation.htm
old-project: display
ms.assetid: 2f5338a9-2a53-4fee-af6a-8a052ef8c423
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DXGKARGCB_CREATECONTEXTALLOCATION, DXGKARGCB_CREATECONTEXTALLOCATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGKARGCB_CREATECONTEXTALLOCATION
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

# _DXGKARGCB_CREATECONTEXTALLOCATION structure



## -description
Specifies the allocation attributes of a GPU context or device-specific context.



## -syntax

````
typedef struct _DXGKARGCB_CREATECONTEXTALLOCATION {
  DXGK_CREATECONTEXTALLOCATIONFLAGS ContextAllocationFlags;
  HANDLE                            hAdapter;
  HANDLE                            hDevice;
  HANDLE                            hContext;
  HANDLE                            hDriverAllocation;
  SIZE_T                            Size;
  UINT                              Alignment;
  UINT                              SupportedSegmentSet;
  UINT                              EvictionSegmentSet;
  DXGK_SEGMENTPREFERENCE            PreferredSegment;
  DXGK_SEGMENTBANKPREFERENCE        HintedBank;
  DXGK_ALLOCATIONINFOFLAGS          Flags;
  HANDLE                            hAllocation;
} DXGKARGCB_CREATECONTEXTALLOCATION;
````


## -struct-fields

### -field ContextAllocationFlags

[in] A <a href="display.dxgk_createcontextallocationflags">DXGK_CREATECONTEXTALLOCATIONFLAGS</a> structure that specifies the properties of the allocation.


### -field hAdapter

[in] A handle to the graphics adapter for which the context allocation is created.


### -field hDevice

[in] A handle to the display device that was originally passed by the DirectX graphics subsystem to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createdevice.md">DxgkDdiCreateDevice</a> function.

<div class="alert"><b>Note</b>  The member is set to <b>NULL</b> for a system device.</div>
<div> </div>

### -field hContext

[in] If <b>ContextAllocationFlags.SharedAcrossContexts</b> is set to a value of 0,
                                                                this member contains the value assigned by the DirectX graphics subsystem for the context that was passed to
                                                                the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_createcontextallocation.md">DxgkCbCreateContextAllocation</a> function.

If <b>ContextAllocationFlags.SharedAcrossContexts</b> is set to a value of 1, this member should be set to <b>NULL</b>.

<div class="alert"><b>Note</b>  The member is also set to <b>NULL</b> for a system context.</div>
<div> </div>

### -field hDriverAllocation

A handle created by the display miniport driver that identifies the created allocation. The value of this member is subsequently passed as the <b>Transfer.hAllocation</b> member of the <a href="display.dxgkarg_buildpagingbuffer">DXGKARG_BUILDPAGINGBUFFER</a> structure that is pointed to by the <i>pBuildPagingBuffer</i> parameter of the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_buildpagingbuffer.md">DxgkDdiBuildPagingBuffer</a> function.


### -field Size

[in] The size, in bytes, that is required for the allocation.


### -field Alignment

[in] The required alignment, in bytes, for the allocation.



### -field SupportedSegmentSet

[in] Segment identifiers that the display miniport driver can set in the <b>PreferredSegment</b> member for read or write operations.


### -field EvictionSegmentSet

[in] Identifiers of segments that can be used for eviction.


### -field PreferredSegment

[in] A <a href="display.dxgk_segmentpreference">DXGK_SEGMENTPREFERENCE</a> structure that indicates the preferred segment identifiers that the display miniport driver requests that the video memory manager use to page-in the allocation.


### -field HintedBank

[in] A <a href="display.dxgk_segmentbankpreference">DXGK_SEGMENTBANKPREFERENCE</a> structure that indicates the bank ordering preferences that the display miniport driver requests that the video memory manager use to page-in the allocation.


### -field Flags

[in] A <a href="display.dxgk_allocationinfoflags">DXGK_ALLOCATIONINFOFLAGS</a> structure that identifies properties for an allocation in bit-field flags. These properties indicate the type of allocation to create. The display miniport driver specifies these flags for the video memory manager. See Remarks for restrictions on flag values.


### -field hAllocation

[out] A handle that has been assigned by the DirectX graphics subsystem to the allocation. This value is subsequently passed as the <b>hAllocation</b> parameter of the  <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_destroycontextallocation.md">DxgkCbDestroyContextAllocation</a> function.


## -remarks
The display miniport driver calls <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_createcontextallocation.md">DxgkCbCreateContextAllocation</a> to allocate a GPU context or device-specific context. When the driver calls this function, it passes a pointer to a <b>DXGKARGCB_CREATECONTEXTALLOCATION</b> structure through the <i>ContextAllocation</i> parameter.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

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
<a href="display.dxgk_allocationinfoflags">DXGK_ALLOCATIONINFOFLAGS</a>
</dt>
<dt>
<a href="display.dxgk_createcontextallocationflags">DXGK_CREATECONTEXTALLOCATIONFLAGS</a>
</dt>
<dt>
<a href="display.dxgk_segmentbankpreference">DXGK_SEGMENTBANKPREFERENCE</a>
</dt>
<dt>
<a href="display.dxgk_segmentpreference">DXGK_SEGMENTPREFERENCE</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_createcontextallocation.md">DxgkCbCreateContextAllocation</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARGCB_CREATECONTEXTALLOCATION structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


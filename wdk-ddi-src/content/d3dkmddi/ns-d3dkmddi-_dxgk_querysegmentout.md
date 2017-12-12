---
UID: NS.D3DKMDDI._DXGK_QUERYSEGMENTOUT
title: _DXGK_QUERYSEGMENTOUT
author: windows-driver-content
description: The DXGK_QUERYSEGMENTOUT structure describes memory-segment information that the display miniport driver should return from a call to its DxgkDdiQueryAdapterInfo function.
old-location: display\dxgk_querysegmentout.htm
old-project: display
ms.assetid: df640b7a-865a-4a8b-94be-ebc60e44cf72
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DXGK_QUERYSEGMENTOUT, DXGK_QUERYSEGMENTOUT
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
req.alt-api: DXGK_QUERYSEGMENTOUT
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

# _DXGK_QUERYSEGMENTOUT structure



## -description
The DXGK_QUERYSEGMENTOUT structure describes memory-segment information that the display miniport driver should return from a call to its <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a> function. 



## -syntax

````
typedef struct _DXGK_QUERYSEGMENTOUT {
  UINT                   NbSegment;
  DXGK_SEGMENTDESCRIPTOR *pSegmentDescriptor;
  UINT                   PagingBufferSegmentId;
  UINT                   PagingBufferSize;
  UINT                   PagingBufferPrivateDataSize;
} DXGK_QUERYSEGMENTOUT;
````


## -struct-fields

### -field NbSegment

[out] The number of memory segments that the driver supports.


### -field pSegmentDescriptor

[out] An array of <a href="display.dxgk_segmentdescriptor">DXGK_SEGMENTDESCRIPTOR</a> structures that the driver populates with information about the segments it supports. The size of the array is the value that <b>NbSegment</b> specifies.


### -field PagingBufferSegmentId

[out] The identifier of the segment that the video memory manager should allocate the paging buffer from. This segment must be an aperture segment.


### -field PagingBufferSize

[out] The size, in bytes, that the video memory manager should allocate for the paging buffer.


### -field PagingBufferPrivateDataSize

[out] The size, in bytes, of the driver-resident private data structure that is associated with each paging buffer. Memory for this private data structure is allocated from nonpaged pool. If the driver specifies zero for <b>PagingBufferPrivateDataSize</b>, no memory is allocated for the private data structure.

The private data structure that is associated with a paging buffer is initialized to zero when the paging buffer is created. During the lifetime of the paging buffer, the video memory manager never accesses the private data structure that is associated with the paging buffer.


## -remarks
The video memory manager allocates a paging buffer either from an aperture segment (if the <b>PagingBufferSegmentId</b> member identifies the segment) or as a contiguous write-combined memory block (if <b>PagingBufferSegmentId</b> is set to 0). If <b>PagingBufferSegmentId</b> is set to 0, the graphics processing unit (GPU) must access direct memory access (DMA) buffers by using PCI cycles on systems where AGP transfers that occur outside the AGP aperture are not permitted.


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
<a href="display.dxgk_querysegmentin">DXGK_QUERYSEGMENTIN</a>
</dt>
<dt>
<a href="display.dxgk_segmentdescriptor">DXGK_SEGMENTDESCRIPTOR</a>
</dt>
<dt>
<a href="display.dxgkarg_queryadapterinfo">DXGKARG_QUERYADAPTERINFO</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_QUERYSEGMENTOUT structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


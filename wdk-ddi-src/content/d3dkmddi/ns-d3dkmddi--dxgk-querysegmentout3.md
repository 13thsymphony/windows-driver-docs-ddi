---
UID: NS.d3dkmddi._DXGK_QUERYSEGMENTOUT3
title: DXGK_QUERYSEGMENTOUT3
author: windows-driver-content
description: Describes memory-segment information that a Windows Display Driver Model (WDDM) 1.2 or later display miniport driver should return from a call to its DxgkDdiQueryAdapterInfo function.
old-location: display\dxgk_querysegmentout3.htm
old-project: display
ms.assetid: 4a78a998-7eab-4499-a280-96ca6d6ff5a2
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGK_QUERYSEGMENTOUT3, DXGK_QUERYSEGMENTOUT3
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_QUERYSEGMENTOUT3
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
req.iface: 
---

# DXGK_QUERYSEGMENTOUT3 structure



## -description
<p>Describes memory-segment information that a Windows Display Driver Model (WDDM) 1.2 or later display miniport driver should return from a call to its <a href="display.dxgkddiqueryadapterinfo">DxgkDdiQueryAdapterInfo</a> function.</p>


## -syntax

````
typedef struct _DXGK_QUERYSEGMENTOUT3 {
  UINT                    NbSegment;
  DXGK_SEGMENTDESCRIPTOR3 *pSegmentDescriptor;
  UINT                    PagingBufferSegmentId;
  UINT                    PagingBufferSize;
  UINT                    PagingBufferPrivateDataSize;
} DXGK_QUERYSEGMENTOUT3;
````


## -struct-fields
<dl>

### -field <b>NbSegment</b>

<dd>
<p>[out] The number of memory segments that the driver supports.</p>
</dd>

### -field <b>pSegmentDescriptor</b>

<dd>
<p>[out] An array of <a href="..\d3dkmddi\ns-d3dkmddi--dxgk-segmentdescriptor3.md">DXGK_SEGMENTDESCRIPTOR3</a> structures that the driver populates with information about the segments it supports. The size of the array is the value that <b>NbSegment</b> specifies.</p>
</dd>

### -field <b>PagingBufferSegmentId</b>

<dd>
<p>[out] The identifier of the segment that the video memory manager should allocate the paging buffer from. This segment must be an aperture segment.</p>
</dd>

### -field <b>PagingBufferSize</b>

<dd>
<p>[out] The size, in bytes, that the video memory manager should allocate for the paging buffer.</p>
</dd>

### -field <b>PagingBufferPrivateDataSize</b>

<dd>
<p>[out] The size, in bytes, of the driver-resident private data structure that is associated with each paging buffer. Memory for this private data structure is allocated from nonpaged pool. If the driver specifies zero for <b>PagingBufferPrivateDataSize</b>, no memory is allocated for the private data structure.</p>
<p>The private data structure that is associated with a paging buffer is initialized to zero when the paging buffer is created. During the lifetime of the paging buffer, the video memory manager never accesses the private data structure that is associated with the paging buffer.</p>
</dd>
</dl>

## -remarks
<p>This structure is used by the  display miniport driver to return information about memory segments in response to a <a href="display.dxgkddiqueryadapterinfo">DxgkDdiQueryAdapterInfo</a> function call in which the graphics subsystem specifies the <b>DXGKQAITYPE_QUERYSEGMENT3</b> value in the <b>Type</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi--dxgkarg-queryadapterinfo.md">DXGKARG_QUERYADAPTERINFO</a> structure.</p>

<p>The video memory manager allocates a paging buffer either from an aperture segment (if the <b>PagingBufferSegmentId</b> member identifies the segment) or as a contiguous write-combined memory block (if <b>PagingBufferSegmentId</b> is set to 0). If <b>PagingBufferSegmentId</b> is set to 0, the GPU must access direct memory access (DMA) buffers by using PCI cycles on systems where AGP transfers that occur outside the AGP aperture are not permitted.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi--dxgk-querysegmentin.md">DXGK_QUERYSEGMENTIN</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi--dxgk-segmentdescriptor3.md">DXGK_SEGMENTDESCRIPTOR3</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi--dxgkarg-queryadapterinfo.md">DXGKARG_QUERYADAPTERINFO</a>
</dt>
<dt>
<a href="display.dxgkddiqueryadapterinfo">DxgkDdiQueryAdapterInfo</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_QUERYSEGMENTOUT3 structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

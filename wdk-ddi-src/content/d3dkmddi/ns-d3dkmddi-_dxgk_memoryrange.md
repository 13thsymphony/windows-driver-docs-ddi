---
UID: NS.D3DKMDDI._DXGK_MEMORYRANGE
title: _DXGK_MEMORYRANGE
author: windows-driver-content
description: DXGK_MEMORYRANGE is used with DxgkDdiQueryAdapterInfo and DXGK_QUERYSEGMENTMEMORYSTATE to query bad graphics processing unit (GPU) memory ranges.
old-location: display\dxgk_memoryrange.htm
old-project: display
ms.assetid: 68B9465D-BA5E-4DE3-8A55-B344399FBB5F
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DXGK_MEMORYRANGE, DXGK_MEMORYRANGE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_MEMORYRANGE
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

# _DXGK_MEMORYRANGE structure



## -description
<b>DXGK_MEMORYRANGE</b> is used with <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a> and <a href="display.dxgk_querysegmentmemorystate">DXGK_QUERYSEGMENTMEMORYSTATE</a> to query bad graphics processing unit (GPU) memory ranges.

The query is done during adapter object initialization. The driver will be called only if <a href="display.dxgk_segmentdescriptor4">DXGK_SEGMENTDESCRIPTOR4</a>::<b>NumInvalidMemoryRanges</b> is not zero for a segment.
  



## -syntax

````
typedef struct _DXGK_MEMORYRANGE {
  UINT64 SegmentOffset;
  UINT64 SizeInBytes;
} DXGK_MEMORYRANGE;
````


## -struct-fields

### -field SegmentOffset

The offset from the start of the segment in bytes. The value must be aligned to the segment page boundary.


### -field SizeInBytes

The number of byte in the range. The value must be multiple of the segment page size.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

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
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a>
</dt>
<dt>
<a href="display.dxgk_segmentdescriptor4">DXGK_SEGMENTDESCRIPTOR4</a>
</dt>
<dt>
<a href="display.dxgk_querysegmentmemorystate">DXGK_QUERYSEGMENTMEMORYSTATE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_MEMORYRANGE structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


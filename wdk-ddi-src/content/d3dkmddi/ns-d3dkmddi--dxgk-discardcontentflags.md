---
UID: NS.d3dkmddi._DXGK_DISCARDCONTENTFLAGS
title: DXGK_DISCARDCONTENTFLAGS
author: windows-driver-content
description: The DXGK_DISCARDCONTENTFLAGS structure identifies the type of discard-content operation to set up in a call to the DxgkDdiBuildPagingBuffer function.
old-location: display\dxgk_discardcontentflags.htm
old-project: display
ms.assetid: 0a93d3a2-0274-4b14-9c4b-9ed31a48e600
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGK_DISCARDCONTENTFLAGS, DXGK_DISCARDCONTENTFLAGS
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
req.alt-api: DXGK_DISCARDCONTENTFLAGS
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

# DXGK_DISCARDCONTENTFLAGS structure



## -description
<p>The DXGK_DISCARDCONTENTFLAGS structure identifies the type of discard-content operation to set up in a call to the <a href="display.dxgkddibuildpagingbuffer">DxgkDdiBuildPagingBuffer</a> function. </p>


## -syntax

````
typedef struct _DXGK_DISCARDCONTENTFLAGS {
  union {
    struct {
      UINT AllocationIsIdle  :1;
      UINT Reserved  :31;
    };
    UINT Value;
  };
} DXGK_DISCARDCONTENTFLAGS;
````


## -struct-fields
<dl>

### -field AllocationIsIdle

<dd>
<p>[in] A UINT value that specifies whether the allocation that is referenced in the call to <a href="display.dxgkddibuildpagingbuffer">DxgkDdiBuildPagingBuffer</a> is idle. If this member is not set, the driver should determine that the allocation is either currently busy or might become busy. If this member is set, the video memory manager guarantees that the allocation remains idle for the duration of the call to <i>DxgkDdiBuildPagingBuffer</i>.</p>
<p>Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001).</p>
</dd>

### -field Reserved

<dd>
<p>[in] This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 31 bits (0xFFFFFFFE) of the 32-bit <b>Value</b> member to zeros.</p>
</dd>

### -field Value

<dd>
<p>[in] A member in the union that DXGK_DISCARDCONTENTFLAGS contains that can hold a 32-bit value that identifies the discard-content-operation type.</p>
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
<a href="..\d3dkmddi\ns-d3dkmddi--dxgkarg-buildpagingbuffer.md">DXGKARG_BUILDPAGINGBUFFER</a>
</dt>
<dt>
<a href="display.dxgkddibuildpagingbuffer">DxgkDdiBuildPagingBuffer</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_DISCARDCONTENTFLAGS structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

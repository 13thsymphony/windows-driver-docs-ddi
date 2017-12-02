---
UID: NS.d3dkmddi._DXGK_OPENALLOCATIONFLAGS
title: DXGK_OPENALLOCATIONFLAGS
author: windows-driver-content
description: The DXGK_OPENALLOCATIONFLAGS structure identifies the operation to perform for allocations.
old-location: display\dxgk_openallocationflags.htm
old-project: display
ms.assetid: 6dae69b1-ff48-4d43-bc01-e7ad7bb7acc9
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGK_OPENALLOCATIONFLAGS, DXGK_OPENALLOCATIONFLAGS
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
req.alt-api: DXGK_OPENALLOCATIONFLAGS
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

# DXGK_OPENALLOCATIONFLAGS structure



## -description
<p>The DXGK_OPENALLOCATIONFLAGS structure identifies the operation to perform for allocations.</p>


## -syntax

````
typedef struct _DXGK_OPENALLOCATIONFLAGS {
  union {
    struct {
      UINT Create  :1;
      UINT ReadOnly  :1;
      UINT Reserved  :30;
    };
    UINT Value;
  };
} DXGK_OPENALLOCATIONFLAGS;
````


## -struct-fields
<dl>

### -field Create

<dd>
<p>A UINT value that specifies whether allocations should be created. If this member is not set, the allocations are opened. </p>
<p>Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b>= member (0x00000001).</p>
</dd>

### -field ReadOnly

<dd>
<p>A UINT value that specifies whether the allocation can only be read from. </p>
<p>Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b>= member (0x00000002).</p>
<p>Supported starting with Windows 8.</p>
</dd>

### -field Reserved

<dd>
<p>This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 30 bits (0xFFFFFFFC) of the 32-bit <b>Value</b> member to zeros.</p>
</dd>

### -field Value

<dd>
<p>A member in the union that DXGK_OPENALLOCATIONFLAGS contains that can hold a 32-bit value that identifies the operation to perform for allocations.</p>
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
<a href="..\d3dkmddi\ns-d3dkmddi--dxgkarg-openallocation.md">DXGKARG_OPENALLOCATION</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_OPENALLOCATIONFLAGS structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

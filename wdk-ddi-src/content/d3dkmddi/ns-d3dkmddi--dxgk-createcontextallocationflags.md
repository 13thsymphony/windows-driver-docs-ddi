---
UID: NS.d3dkmddi._DXGK_CREATECONTEXTALLOCATIONFLAGS
title: DXGK_CREATECONTEXTALLOCATIONFLAGS
author: windows-driver-content
description: Specifies the properties of the context to be allocated.
old-location: display\dxgk_createcontextallocationflags.htm
old-project: display
ms.assetid: e80a314d-cef1-4289-84db-0a6b6531ae5f
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGK_CREATECONTEXTALLOCATIONFLAGS, DXGK_CREATECONTEXTALLOCATIONFLAGS
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
req.alt-api: DXGK_CREATECONTEXTALLOCATIONFLAGS
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

# DXGK_CREATECONTEXTALLOCATIONFLAGS structure



## -description
<p>Specifies the properties of the context to be allocated.</p>


## -syntax

````
typedef struct _DXGK_CREATECONTEXTALLOCATIONFLAGS {
  union {
    struct {
      UINT SharedAcrossContexts  :1;
      UINT Reserved  :31;
    };
    UINT Value;
  };
} DXGK_CREATECONTEXTALLOCATIONFLAGS;
````


## -struct-fields
<dl>

### -field SharedAcrossContexts

<dd>
<p>[in] A UINT value that specifies the association of the context.</p>
<p>If <b>SharedAcrossContexts</b> is set to one, the allocation is associated with all contexts specified by the <b>hDevice</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi--dxgkargcb-createcontextallocation.md">DXGKARGCB_CREATECONTEXTALLOCATION</a> structure. The allocated context will be made resident when any context that belongs to <b>hDevice</b> is
                                                            scheduled to run on the GPU.</p>
<p>If <b>SharedAcrossContexts</b> is set to zero, the allocation is associated with the context specified by the <b>hContext</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi--dxgkargcb-createcontextallocation.md">DXGKARGCB_CREATECONTEXTALLOCATION</a> structure. The allocated context will be made resident when <b>hContext</b> is scheduled to run on the GPU.
                                                            </p>
</dd>

### -field Reserved

<dd>
<p>[in] This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the most significant 31 bits (0xFFFFFFFE) to zeros.
</p>
</dd>

### -field Value

<dd>
<p>[in] A 32-bit value that specifies the context allocation flags.</p>
</dd>
</dl>

## -remarks
<p>The display miniport driver allocates GPU contexts or device-specific contexts by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb-createcontextallocation.md">DxgkCbCreateContextAllocation</a>.</p>

<p>The <b>ContextAllocationFlags</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi--dxgkargcb-createcontextallocation.md">DXGKARGCB_CREATECONTEXTALLOCATION</a> structure is an <b>DXGK_CREATECONTEXTALLOCATIONFLAGS</b> data type. 
 </p>

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
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi--dxgkargcb-createcontextallocation.md">DXGKARGCB_CREATECONTEXTALLOCATION</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb-createcontextallocation.md">DxgkCbCreateContextAllocation</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20 DXGK_CREATECONTEXTALLOCATIONFLAGS structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

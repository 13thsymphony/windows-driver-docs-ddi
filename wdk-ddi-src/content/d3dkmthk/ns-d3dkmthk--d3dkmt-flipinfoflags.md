---
UID: NS.d3dkmthk._D3DKMT_FLIPINFOFLAGS
title: D3DKMT_FLIPINFOFLAGS
author: windows-driver-content
description: The D3DKMT_FLIPINFOFLAGS structure identifies flipping capabilities of the display miniport driver that the OpenGL installable client driver (ICD) obtains by calling the D3DKMTQueryAdapterInfo function.
old-location: display\d3dkmt_flipinfoflags.htm
old-project: display
ms.assetid: 61b6d477-5a4c-475c-8605-5ede592e75c1
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DKMT_FLIPINFOFLAGS, D3DKMT_FLIPINFOFLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_FLIPINFOFLAGS
req.alt-loc: d3dkmthk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.iface: 
---

# D3DKMT_FLIPINFOFLAGS structure



## -description
<p>The D3DKMT_FLIPINFOFLAGS structure identifies flipping capabilities of the display miniport driver that the OpenGL installable client driver (ICD) obtains by calling the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtqueryadapterinfo.md">D3DKMTQueryAdapterInfo</a> function.</p>


## -syntax

````
typedef struct _D3DKMT_FLIPINFOFLAGS {
  UINT FlipInterval  :1;
  UINT Reserved  :31;
} D3DKMT_FLIPINFOFLAGS;
````


## -struct-fields
<dl>

### -field <b>FlipInterval</b>

<dd>
<p>A UINT value that specifies whether the display miniport driver natively supports the scheduling of a flip command to take effect after two, three or four vertical syncs occur. Regardless of whether the display miniport driver supports a flip interval of two or greater, the driver must support an immediate flip and a flip interval of one.</p>
<p>Setting this member is equivalent to setting the first bit of a 32-bit value (0x00000001).</p>
</dd>

### -field <b>Reserved</b>

<dd>
<p>This member is reserved and should be set to zero. Setting this member is equivalent to setting the remaining 31 bits (0xFFFFFFFE) of a 32-bit value to zeros. </p>
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
<dt>D3dkmthk.h (include D3dkmthk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dkmthk\ns-d3dkmthk--d3dkmt-flipqueueinfo.md">D3DKMT_FLIPQUEUEINFO</a>
</dt>
<dt>
<a href="..\d3dkmthk\ns-d3dkmthk--d3dkmt-queryadapterinfo.md">D3DKMT_QUERYADAPTERINFO</a>
</dt>
<dt>
<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtqueryadapterinfo.md">D3DKMTQueryAdapterInfo</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_FLIPINFOFLAGS structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

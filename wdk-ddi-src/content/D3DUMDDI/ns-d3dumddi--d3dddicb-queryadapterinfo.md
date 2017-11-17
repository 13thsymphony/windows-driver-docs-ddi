---
UID: NS.d3dumddi._D3DDDICB_QUERYADAPTERINFO
title: D3DDDICB_QUERYADAPTERINFO
author: windows-driver-content
description: The D3DDDICB_QUERYADAPTERINFO structure contains information that describes the graphics adapter.
old-location: display\d3dddicb_queryadapterinfo.htm
ms.assetid: 484406a5-54be-49fa-839a-2e55747020f4
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: display
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDICB_QUERYADAPTERINFO
req.alt-loc: d3dumddi.h
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
ms.keywords: D3DDDICB_QUERYADAPTERINFO, D3DDDICB_QUERYADAPTERINFO
req.iface: 
---

# D3DDDICB_QUERYADAPTERINFO structure



## -description
<p>The D3DDDICB_QUERYADAPTERINFO structure contains information that describes the graphics adapter.</p>


## -syntax

````
typedef struct _D3DDDICB_QUERYADAPTERINFO {
  VOID *pPrivateDriverData;
  UINT PrivateDriverDataSize;
} D3DDDICB_QUERYADAPTERINFO;
````


## -struct-fields
<dl>

### -field <b>pPrivateDriverData</b>

<dd>
<p>[out] A pointer to a buffer that the display miniport driver can fill with information about the graphics adapter.</p>
</dd>

### -field <b>PrivateDriverDataSize</b>

<dd>
<p>[in/out] The size, in bytes, of the buffer that <b>pPrivateDriverData</b> points to.</p>
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
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/8008574f-a89e-4fed-b745-7cf5baa68e64">pfnQueryAdapterInfoCb</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_QUERYADAPTERINFO structure%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

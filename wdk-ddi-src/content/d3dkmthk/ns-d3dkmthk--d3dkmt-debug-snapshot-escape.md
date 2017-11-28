---
UID: NS.d3dkmthk._D3DKMT_DEBUG_SNAPSHOT_ESCAPE
title: D3DKMT_DEBUG_SNAPSHOT_ESCAPE
author: windows-driver-content
description: Do not use the D3DKMT_DEBUG_SNAPSHOT_ESCAPE structure; it is for testing purposes only. The D3DKMT_DEBUG_SNAPSHOT_ESCAPE structure describes a debug snapshot that is returned in a call to the D3DKMTEscape function.
old-location: display\d3dkmt_debug_snapshot_escape.htm
old-project: display
ms.assetid: f5aa4829-6264-444c-b8e6-23854cb87534
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DKMT_DEBUG_SNAPSHOT_ESCAPE, D3DKMT_DEBUG_SNAPSHOT_ESCAPE
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
req.alt-api: D3DKMT_DEBUG_SNAPSHOT_ESCAPE
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

# D3DKMT_DEBUG_SNAPSHOT_ESCAPE structure



## -description
<p>
   Do not use the D3DKMT_DEBUG_SNAPSHOT_ESCAPE structure; it is for testing purposes only.
   </p>
<p>The D3DKMT_DEBUG_SNAPSHOT_ESCAPE structure describes a debug snapshot that is returned in a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546940">D3DKMTEscape</a> function.</p>


## -syntax

````
typedef struct _D3DKMT_DEBUG_SNAPSHOT_ESCAPE {
  ULONG Length;
  BYTE  Buffer[1];
} D3DKMT_DEBUG_SNAPSHOT_ESCAPE;
````


## -struct-fields
<dl>

### -field <b>Length</b>

<dd>
<p>[out] The actual length of the snapshot written in the <b>Buffer</b> member.</p>
</dd>

### -field <b>Buffer</b>

<dd>
<p>[out] The buffer to place the snapshot in.</p>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547970">D3DKMT_ESCAPE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546940">D3DKMTEscape</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_DEBUG_SNAPSHOT_ESCAPE structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

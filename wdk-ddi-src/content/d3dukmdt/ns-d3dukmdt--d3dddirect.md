---
UID: NS.d3dukmdt._D3DDDIRECT
title: D3DDDIRECT
author: windows-driver-content
description: The D3DDDIRECT structure defines a rectangle by the coordinates of its upper-left and lower-right corners.
old-location: display\d3dddirect.htm
old-project: display
ms.assetid: 7dcb4b17-3aac-46df-9aed-d2145ed3034a
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DDDIRECT, D3DDDIRECT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dukmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDIRECT
req.alt-loc: d3dukmdt.h
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

# D3DDDIRECT structure



## -description
<p>The D3DDDIRECT structure defines a rectangle by the coordinates of its upper-left and lower-right corners.</p>


## -syntax

````
typedef struct _D3DDDIRECT {
  LONG left;
  LONG top;
  LONG right;
  LONG bottom;
} D3DDDIRECT;
````


## -struct-fields
<dl>

### -field <b>left</b>

<dd>
<p>[in] The x-coordinate of the upper-left corner of the rectangle.</p>
</dd>

### -field <b>top</b>

<dd>
<p>[in] The y-coordinate of the upper-left corner of the rectangle.</p>
</dd>

### -field <b>right</b>

<dd>
<p>[in] The x-coordinate of the lower-right corner of the rectangle.</p>
</dd>

### -field <b>bottom</b>

<dd>
<p>[in] The y-coordinate of the lower-right corner of the rectangle.</p>
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
<dt>D3dukmdt.h (include D3dukmdt.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544577">D3DDDI_KERNELOVERLAYINFO</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIRECT structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

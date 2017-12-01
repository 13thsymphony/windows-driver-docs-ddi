---
UID: NS.d3dkmthk._D3DKMT_GETSCANLINE
title: D3DKMT_GETSCANLINE
author: windows-driver-content
description: The D3DKMT_GETSCANLINE structure contains information about a video present source's vertical blanking status.
old-location: display\d3dkmt_getscanline.htm
old-project: display
ms.assetid: af06c31e-0c4f-4e2a-8d19-84c1c63d6bd0
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DKMT_GETSCANLINE, D3DKMT_GETSCANLINE
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
req.alt-api: D3DKMT_GETSCANLINE
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

# D3DKMT_GETSCANLINE structure



## -description
<p>The D3DKMT_GETSCANLINE structure contains information about a video present source's vertical blanking status.</p>


## -syntax

````
typedef struct _D3DKMT_GETSCANLINE {
  D3DKMT_HANDLE                  hAdapter;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
  BOOLEAN                        InVerticalBlank;
  UINT                           ScanLine;
} D3DKMT_GETSCANLINE;
````


## -struct-fields
<dl>

### -field <b>hAdapter</b>

<dd>
<p>[in] A handle to a graphics adapter.</p>
</dd>

### -field <b>VidPnSourceId</b>

<dd>
<p>[in] The identifier of a graphics adapter's video present source.</p>
</dd>

### -field <b>InVerticalBlank</b>

<dd>
<p>[out] A Boolean variable that receives <b>TRUE</b> if the video present source is in vertical blanking mode and <b>FALSE</b> if the video present source is not in vertical blanking mode.</p>
</dd>

### -field <b>ScanLine</b>

<dd>
<p>[out] The video present source's current scan line.</p>
</dd>
</dl>

## -remarks
<p>A video present path represents a connection between a video present source (view) and a video present target (output) on a graphics adapter. For more information about video present networks, paths, sources, and targets, see <a href="https://msdn.microsoft.com/62a92f00-b1da-41c2-99af-eef8140b064e">Introduction to Video Present Networks</a>.</p>

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
<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtgetscanline.md">D3DKMTGetScanLine</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_GETSCANLINE structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

---
UID: NS.d3dumddi._D3DDDI_OVERLAYINFO
title: D3DDDI_OVERLAYINFO
author: windows-driver-content
description: The D3DDDI_OVERLAYINFO structure describes information about an overlay.
old-location: display\d3dddi_overlayinfo.htm
old-project: display
ms.assetid: e2732ea9-4fd6-416d-8fb0-1ccf1d1ad0df
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DDDI_OVERLAYINFO, D3DDDI_OVERLAYINFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDI_OVERLAYINFO
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
req.iface: 
---

# D3DDDI_OVERLAYINFO structure



## -description
<p>The D3DDDI_OVERLAYINFO structure describes information about an overlay. </p>


## -syntax

````
typedef struct _D3DDDI_OVERLAYINFO {
  HANDLE                  hResource;
  UINT                    SubResourceIndex;
  RECT                    DstRect;
  RECT                    SrcRect;
  UINT                    DstColorKeyLow;
  UINT                    DstColorKeyHigh;
  UINT                    SrcColorKeyLow;
  UINT                    SrcColorKeyHigh;
  D3DDDI_OVERLAYINFOFLAGS Flags;
} D3DDDI_OVERLAYINFO;
````


## -struct-fields
<dl>

### -field <b>hResource</b>

<dd>
<p>[in] A handle to the resource that is displayed by using the overlay. The resource is created through a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-createresource.md">CreateResource</a> function with the <b>Overlay</b> bit-field flag set in the <b>Flags</b> member of the <a href="..\d3dukmdt\ns-d3dukmdt--d3dddiarg-createresource.md">D3DDDIARG_CREATERESOURCE</a> structure that is pointed to by the <i>pResource</i> parameter.</p>
</dd>

### -field <b>SubResourceIndex</b>

<dd>
<p>[in] The index to the subresource if the resource that is specified by the <b>hResource</b> member contains a list of allocations. </p>
</dd>

### -field <b>DstRect</b>

<dd>
<p>[in] A <a href="display.rect">RECT</a> structure for the destination rectangle, which contains the output coordinates for the display. </p>
</dd>

### -field <b>SrcRect</b>

<dd>
<p>[in] A RECT structure for the source rectangle that is displayed. </p>
</dd>

### -field <b>DstColorKeyLow</b>

<dd>
<p>[in] A value for the destination color key when the <b>DstColorKey</b> bit-field flag is set in the <b>Flags</b> member. If the color key is a range, <b>DstColorKeyLow</b> contains the low end of the range. The value is in the native format of the primary surface that is overlayed. </p>
</dd>

### -field <b>DstColorKeyHigh</b>

<dd>
<p>[in] The high end of the destination color key range when the <b>DstColorKeyRange</b> bit-field flag is set in <b>Flags</b>. The value is in the native format of the primary surface that is overlayed. </p>
</dd>

### -field <b>SrcColorKeyLow</b>

<dd>
<p>[in] A value for the source color key when the <b>SrcColorKey</b> bit-field flag is set in the <b>Flags</b> member. If the color key is a range, <b>SrcColorKeyLow</b> contains the low end of the range. The value is in the native format of the overlay resource that is displayed. </p>
</dd>

### -field <b>SrcColorKeyHigh</b>

<dd>
<p>[in] The high end of the source color key range when the <b>SrcColorKeyRange</b> bit-field flag is set in <b>Flags</b>. The value is in the native format of the overlay resource that is displayed. </p>
</dd>

### -field <b>Flags</b>

<dd>
<p>[in] A <a href="..\d3dumddi\ns-d3dumddi--d3dddi-overlayinfoflags.md">D3DDDI_OVERLAYINFOFLAGS</a> structure that identifies the type of overlay operation to perform. Note that some flags are mutually exclusive with other flags. For more information, see the following Remarks section.</p>
</dd>
</dl>

## -remarks
<p>The <b>SrcColorKey</b>, <b>SrcColorKeyRange</b>, <b>DstColorKey</b>, and <b>DstColorKeyRange</b> bit-field flags are never set simultaneously in the <b>Flags</b> member. </p>

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
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-createoverlay.md">CreateOverlay</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-createresource.md">CreateResource</a>
</dt>
<dt>
<a href="..\d3dukmdt\ns-d3dukmdt--d3dddiarg-createresource.md">D3DDDIARG_CREATERESOURCE</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi--d3dddi-overlayinfoflags.md">D3DDDI_OVERLAYINFOFLAGS</a>
</dt>
<dt>
<a href="display.rect">RECT</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-updateoverlay.md">UpdateOverlay</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_OVERLAYINFO structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

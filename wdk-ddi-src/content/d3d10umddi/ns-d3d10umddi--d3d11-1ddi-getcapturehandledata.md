---
UID: NS.d3d10umddi._D3D11_1DDI_GETCAPTUREHANDLEDATA
title: D3D11_1DDI_GETCAPTUREHANDLEDATA
author: windows-driver-content
description: Defines a resource allocation in a call to the GetCaptureHandle function.
old-location: display\d3d11_1ddi_getcapturehandledata.htm
old-project: display
ms.assetid: f12ace3a-2bb4-433b-b987-2027a48f4c14
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3D11_1DDI_GETCAPTUREHANDLEDATA, D3D11_1DDI_GETCAPTUREHANDLEDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D11_1DDI_GETCAPTUREHANDLEDATA
req.alt-loc: D3d10umddi.h
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

# D3D11_1DDI_GETCAPTUREHANDLEDATA structure



## -description
<p>Defines a resource allocation in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11-1ddi-getcapturehandle.md">GetCaptureHandle</a> function.</p>


## -syntax

````
typedef struct _D3D11_1DDI_GETCAPTUREHANDLEDATA {
  D3D10DDI_HRESOURCE hResource;
  UINT               ArrayIndex;
  D3DKMT_HANDLE      hAllocation;
  UINT               DataOffset;
  UINT               DataSize;
} D3D11_1DDI_GETCAPTUREHANDLEDATA;
````


## -struct-fields
<dl>

### -field hResource

<dd>
<p>[in] The handle to the resource for which the allocation handle is to be obtained.</p>
<p>The Direct3D version 11 and later runtime will have already verified that this resource was created using the <b>D3D11_DDI_BIND_CAPTURE</b> value in the <a href="..\d3d10umddi\ne-d3d10umddi-d3d10-ddi-resource-bind-flag.md">D3D10_DDI_RESOURCE_BIND_FLAG</a> enumeration.</p>
</dd>

### -field ArrayIndex

<dd>
<p>[in] The array element from which the data is to be obtained.</p>
<p>If the resource was not created as a texture array, this value is zero. For a texture array, the Direct3D version 11 and later runtime will have already verified that the array is valid.</p>
</dd>

### -field hAllocation

<dd>
<p>[out] The driver-provided address of the kernel mode allocation handle associated with this allocation.</p>
</dd>

### -field DataOffset

<dd>
<p>[out] The driver-provided offset of the requested data within the allocation.</p>
<p>If the resource was not created as a texture array, this value is typically zero.  For a texture array, this value is the offset of the array element data within the allocation.</p>
</dd>

### -field DataSize

<dd>
<p>[out] The driver-provided size of the requested data within the allocation.</p>
<p>If the resource was not created as a texture array, this value is typically the size of the allocation, in bytes.  For a texture array, this value is the size of the element data within the allocation.</p>
</dd>
</dl>

## -remarks
<p>When the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11-1ddi-getcapturehandle.md">GetCaptureHandle</a> function is called, the driver updates the structure with the kernel mode allocation handle associated with the specified resource, as well as the size of the resource data and its offset within an allocated block of memory.</p>

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
<dt>D3d10umddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\ne-d3d10umddi-d3d10-ddi-resource-bind-flag.md">D3D10_DDI_RESOURCE_BIND_FLAG</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11-1ddi-getcapturehandle.md">GetCaptureHandle</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1DDI_GETCAPTUREHANDLEDATA structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

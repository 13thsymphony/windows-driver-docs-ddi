---
UID: NS.d3d10umddi.D3D10DDI_MAPPED_SUBRESOURCE
title: D3D10DDI_MAPPED_SUBRESOURCE
author: windows-driver-content
description: The D3D10DDI_MAPPED_SUBRESOURCE structure describes a subresource that the driver maps to through a call to the driver's ResourceMap function.
old-location: display\d3d10ddi_mapped_subresource.htm
old-project: display
ms.assetid: a55f9aee-c6a5-4391-aad1-4003e58692cd
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3D10DDI_MAPPED_SUBRESOURCE, D3D10DDI_MAPPED_SUBRESOURCE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with  Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D10DDI_MAPPED_SUBRESOURCE
req.alt-loc: d3d10umddi.h
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

# D3D10DDI_MAPPED_SUBRESOURCE structure



## -description
<p>The D3D10DDI_MAPPED_SUBRESOURCE structure describes a subresource that the driver maps to through a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-resourcemap.md">ResourceMap</a> function.</p>


## -syntax

````
typedef struct D3D10DDI_MAPPED_SUBRESOURCE {
  void *pData;
  UINT RowPitch;
  UINT DepthPitch;
} D3D10DDI_MAPPED_SUBRESOURCE;
````


## -struct-fields
<dl>

### -field <b>pData</b>

<dd>
<p>[out] A pointer to a buffer that contains the contents of the subresource.</p>
</dd>

### -field <b>RowPitch</b>

<dd>
<p>[out] The row pitch,  width, or physical size (in bytes) of the data.</p>
</dd>

### -field <b>DepthPitch</b>

<dd>
<p>[out] The deptch pitch,  width, or physical size (in bytes) of the data.</p>
</dd>
</dl>

## -remarks
<p>The <b>pData</b> member points to row 0 and slice 0.</p>

<p>The <b>RowPitch</b> member is the value that is added to <b>pData</b> to move from row to row. Each row should contain multiple pixels.</p>

<p>The <b>DepthPitch</b> member is the value that is added to <b>pData</b> to move from depth slice to depth slice. Each depth slice should contain multiple rows.</p>

<p>It is not advisable to assign a value of zero to the <b>RowPitch</b> and <b>DepthPitch</b> members.</p>

<p>To avoid zero values for these members, it helps to think of all  resources as being three-dimensional, as in these two examples:</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with  Windows Vista.</p>
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
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-resourcemap.md">ResourceMap</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10DDI_MAPPED_SUBRESOURCE structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

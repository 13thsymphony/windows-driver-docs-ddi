---
UID: NS.d3dukmdt._D3DDDIARG_CREATERESOURCE
title: D3DDDIARG_CREATERESOURCE
author: windows-driver-content
description: The D3DDDIARG_CREATERESOURCE structure contains information for creating a resource.
old-location: display\d3dddiarg_createresource.htm
old-project: display
ms.assetid: 022047a4-105e-4859-ba37-fb408f903e7b
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DDDIARG_CREATERESOURCE, D3DDDIARG_CREATERESOURCE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDIARG_CREATERESOURCE
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

# D3DDDIARG_CREATERESOURCE structure



## -description
<p>The D3DDDIARG_CREATERESOURCE structure contains information for creating a resource.</p>


## -syntax

````
typedef struct _D3DDDIARG_CREATERESOURCE {
  D3DDDIFORMAT                   Format;
  D3DDDI_POOL                    Pool;
  D3DDDIMULTISAMPLE_TYPE         MultisampleType;
  UINT                           MultisampleQuality;
  const D3DDDI_SURFACEINFO       *pSurfList;
  UINT                           SurfCount;
  UINT                           MipLevels;
  UINT                           Fvf;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
  D3DDDI_RATIONAL                RefreshRate;
  HANDLE                         hResource;
  D3DDDI_RESOURCEFLAGS           Flags;
  D3DDDI_ROTATION                Rotation;
} D3DDDIARG_CREATERESOURCE;
````


## -struct-fields
<dl>

### -field <b>Format</b>

<dd>
<p>[in] A <a href="..\d3dukmdt\ne-d3dukmdt--d3dddiformat.md">D3DDDIFORMAT</a>-typed value that indicates the format of the resources.</p>
</dd>

### -field <b>Pool</b>

<dd>
<p>[in] A <a href="..\d3dukmdt\ne-d3dukmdt--d3dddi-pool.md">D3DDDI_POOL</a>-typed value that indicates the type of memory pool that the resources are created from.</p>
</dd>

### -field <b>MultisampleType</b>

<dd>
<p>[in] A <a href="..\d3dukmdt\ne-d3dukmdt--d3dddimultisample-type.md">D3DDDIMULTISAMPLE_TYPE</a>-typed value that indicates the number of samples for a multiple-sampled surface. If the surface is not multiple sampled, this value is D3DDDIMULTISAMPLE_NONE (0).</p>
</dd>

### -field <b>MultisampleQuality</b>

<dd>
<p>[in] The quality level of rendering samples in a multiple-sampled surface. The quality level must be a number from 0 through 7 that represents a quality level from 1 through 8, respectively.</p>
<p>Note that even if the surface is not multiple-sampled (that is, if <b>D3DDDIMULTISAMPLE_NONE</b> is specified in <b>MultisampleType</b>) it can still have a quality level that is greater than 1 (which is specified by using a number greater than 0).</p>
</dd>

### -field <b>pSurfList</b>

<dd>
<p>[in] An array of <a href="..\d3dukmdt\ns-d3dukmdt--d3dddi-surfaceinfo.md">D3DDDI_SURFACEINFO</a> structures for the list of surfaces (or other resource types) to create.</p>
</dd>

### -field <b>SurfCount</b>

<dd>
<p>[in] The number of resources in the array that is specified by the <b>pSurfList</b> member.</p>
</dd>

### -field <b>MipLevels</b>

<dd>
<p>[in] The number of MIP-map levels for the resources.</p>
</dd>

### -field <b>Fvf</b>

<dd>
<p>[in] The FVF format for vertex buffers.</p>
</dd>

### -field <b>VidPnSourceId</b>

<dd>
<p>[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the primary surface is created on (if the resource contains a primary surface). </p>
</dd>

### -field <b>RefreshRate</b>

<dd>
<p>[in] A <a href="..\d3dukmdt\ns-d3dukmdt--d3dddi-rational.md">D3DDDI_RATIONAL</a> structure that specifies the refresh rate that the resource is used with. This member is applicable only if the resource is the primary surface and the <b>MatchGdiPrimary</b> bit-field flag is not set in the <b>Flags</b> member. In addition, if the <b>InterlacedRefresh</b> bit-field flag is set in <b>Flags</b>, the user-mode display driver determines that the refresh rate is interleaved (otherwise, progressive).</p>
</dd>

### -field <b>hResource</b>

<dd>
<p>[in/out] A handle to the resource. On input to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-createresource.md">CreateResource</a> function, <b>hResource</b> specifies the handle that the driver should use anytime it calls back into the Microsoft Direct3D runtime. </p>
<p>The driver generates a unique handle and passes it back to the Direct3D runtime. On output from the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-createresource.md">CreateResource</a> function, <b>hResource</b> specifies the handle that the Direct3D runtime should use in subsequent driver calls to identify the resource.</p>
</dd>

### -field <b>Flags</b>

<dd>
<p>[in] A <a href="..\d3dukmdt\ns-d3dukmdt--d3dddi-resourceflags.md">D3DDDI_RESOURCEFLAGS</a> structure that identifies the type of resources to create. Note that some of the bit-field flags in <b>D3DDDI_RESOURCEFLAGS</b> require that additional bit-field flags are set as well.</p>
</dd>

### -field <b>Rotation</b>

<dd>
<p>[in] A <a href="..\d3dukmdt\ne-d3dukmdt--d3dddi-rotation.md">D3DDDI_ROTATION</a>-typed value that identifies the orientation of the resource. </p>
<p>For example, consider that the user-mode display driver receives a request for a 480x640 surface to be rotated 90 degrees (<b>D3DDDI_ROTATION_90</b>). The driver should allocate the surface in 640x480 mode for scanning purposes. When rendering to the surface, the driver should perform the 90 degree rotation. </p>
<p>Orientations other than <b>D3DDDI_ROTATION_IDENTITY</b> are set only when the <b>Primary</b> bit-field flag is also set in the <b>Flags</b> member.</p>
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
<dt>D3dukmdt.h (include D3dumddi.h or D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-createresource.md">CreateResource</a>
</dt>
<dt>
<a href="..\d3dukmdt\ne-d3dukmdt--d3dddiformat.md">D3DDDIFORMAT</a>
</dt>
<dt>
<a href="..\d3dukmdt\ne-d3dukmdt--d3dddimultisample-type.md">D3DDDIMULTISAMPLE_TYPE</a>
</dt>
<dt>
<a href="..\d3dukmdt\ne-d3dukmdt--d3dddi-pool.md">D3DDDI_POOL</a>
</dt>
<dt>
<a href="..\d3dukmdt\ns-d3dukmdt--d3dddi-rational.md">D3DDDI_RATIONAL</a>
</dt>
<dt>
<a href="..\d3dukmdt\ne-d3dukmdt--d3dddi-rotation.md">D3DDDI_ROTATION</a>
</dt>
<dt>
<a href="..\d3dukmdt\ns-d3dukmdt--d3dddi-surfaceinfo.md">D3DDDI_SURFACEINFO</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_CREATERESOURCE structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

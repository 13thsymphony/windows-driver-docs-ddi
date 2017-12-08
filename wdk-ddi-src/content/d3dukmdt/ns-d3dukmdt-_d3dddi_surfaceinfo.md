---
UID: NS.D3DUKMDT._D3DDDI_SURFACEINFO
title: _D3DDDI_SURFACEINFO
author: windows-driver-content
description: The D3DDDI_SURFACEINFO structure describes a resource type, such as a surface.
old-location: display\d3dddi_surfaceinfo.htm
old-project: display
ms.assetid: 347edff7-b209-4b60-aabc-5ee7963c8164
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _D3DDDI_SURFACEINFO, D3DDDI_SURFACEINFO
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
req.alt-api: D3DDDI_SURFACEINFO
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
---

# _D3DDDI_SURFACEINFO structure



## -description
The D3DDDI_SURFACEINFO structure describes a resource type, such as a surface.


## -syntax

````
typedef struct _D3DDDI_SURFACEINFO {
  UINT       Width;
  UINT       Height;
  UINT       Depth;
  const VOID *pSysMem;
  UINT       SysMemPitch;
  UINT       SysMemSlicePitch;
} D3DDDI_SURFACEINFO;
````


## -struct-fields

### -field Width

[in] The width, in pixels, of the surface or volume or the length, in pixels, of the linear resource.

### -field Height

[in] The height, in pixels, of the surface or volume.

### -field Depth

[in] The depth, in pixels, of the volume.

### -field pSysMem

[in] A pointer to a buffer that contains the contents of the resource if the resource exists in system memory and <b>NULL</b> if the resource exists in video memory.
Note that this member is valid only if the <b>Pool</b> member of the <a href="display.d3dddiarg_createresource">D3DDDIARG_CREATERESOURCE</a> structure for creating the resource is set to the D3DDDIPOOL_SYSTEMMEM value.

### -field SysMemPitch

[in] The pitch, in bytes, of the surface--that is, the distance, in bytes, to the start of the next line.

### -field SysMemSlicePitch

[in] The slice, in bytes, of the volume.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.
</td>
</tr>
<tr>
<th width="30%">
Header
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
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource.md">CreateResource</a>
</dt>
<dt>
<a href="display.d3dddiarg_createresource">D3DDDIARG_CREATERESOURCE</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_SURFACEINFO structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

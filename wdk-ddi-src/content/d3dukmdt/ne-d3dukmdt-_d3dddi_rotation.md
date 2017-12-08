---
UID: NE.d3dukmdt._D3DDDI_ROTATION
title: _D3DDDI_ROTATION
author: windows-driver-content
description: The D3DDDI_ROTATION enumeration type contains values that identify the orientation of a resource.
old-location: display\d3dddi_rotation.htm
old-project: display
ms.assetid: c167b958-bd09-441e-9680-f193da5ad77f
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _D3DDDI_ROTATION, D3DDDI_ROTATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDI_ROTATION
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

# _D3DDDI_ROTATION enumeration



## -description
The D3DDDI_ROTATION enumeration type contains values that identify the orientation of a resource.


## -syntax

````
typedef enum _D3DDDI_ROTATION { 
  D3DDDI_ROTATION_IDENTITY  = 1,
  D3DDDI_ROTATION_90        = 2,
  D3DDDI_ROTATION_180       = 3,
  D3DDDI_ROTATION_270       = 4
} D3DDDI_ROTATION;
````


## -enum-fields

### -field D3DDDI_ROTATION_IDENTITY

Indicates that the resource is not rotated. 

### -field D3DDDI_ROTATION_90

Indicates that the resource is rotated 90 degrees. 

### -field D3DDDI_ROTATION_180

Indicates that the resource is rotated 180 degrees. 

### -field D3DDDI_ROTATION_270

Indicates that the resource is rotated 270 degrees. 

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
<a href="display.d3dddiarg_createresource">D3DDDIARG_CREATERESOURCE</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_ROTATION enumeration%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

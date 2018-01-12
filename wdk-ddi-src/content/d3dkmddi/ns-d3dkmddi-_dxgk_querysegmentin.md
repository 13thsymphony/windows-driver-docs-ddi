---
UID: NS:d3dkmddi._DXGK_QUERYSEGMENTIN
title: _DXGK_QUERYSEGMENTIN
author: windows-driver-content
description: The DXGK_QUERYSEGMENTIN structure describes relevant information for a memory-segment query through a call to the display miniport driver's DxgkDdiQueryAdapterInfo function.
old-location: display\dxgk_querysegmentin.htm
old-project: display
ms.assetid: 5a3e6edf-40c7-49f3-8394-0e54c080c92c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_QUERYSEGMENTIN, DXGK_QUERYSEGMENTIN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_QUERYSEGMENTIN
req.alt-loc: d3dkmddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: DXGK_QUERYSEGMENTIN
---

# _DXGK_QUERYSEGMENTIN structure



## -description
The DXGK_QUERYSEGMENTIN structure describes relevant information for a memory-segment query through a call to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a> function. 



## -syntax

````
typedef struct _DXGK_QUERYSEGMENTIN {
  PHYSICAL_ADDRESS  AgpApertureBase;
  LARGE_INTEGER     AgpApertureSize;
  DXGK_SEGMENTFLAGS AgpFlags;
} DXGK_QUERYSEGMENTIN;
````


## -struct-fields

### -field AgpApertureBase

[in] A PHYSICAL_ADDRESS data type (which is defined as LARGE_INTEGER) that indicates the base address of the AGP aperture. 


### -field AgpApertureSize

[in] A LARGE_INTEGER that indicates the size, in bytes, of the available AGP aperture.


### -field AgpFlags

[in] A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_segmentflags.md">DXGK_SEGMENTFLAGS</a> structure that identifies properties for the available AGP aperture in bit-field flags.


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
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_querysegmentout.md">DXGK_QUERYSEGMENTOUT</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_segmentdescriptor.md">DXGK_SEGMENTDESCRIPTOR</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_segmentflags.md">DXGK_SEGMENTFLAGS</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_queryadapterinfo.md">DXGKARG_QUERYADAPTERINFO</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_QUERYSEGMENTIN structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


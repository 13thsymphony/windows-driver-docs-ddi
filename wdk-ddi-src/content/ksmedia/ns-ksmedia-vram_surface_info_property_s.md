---
UID: NS.KSMEDIA.VRAM_SURFACE_INFO_PROPERTY_S
title: VRAM_SURFACE_INFO_PROPERTY_S
author: windows-driver-content
description: The VRAM_SURFACE_INFO_PROPERTY_S structure describes property items in the KSPROPSETID_VramCapture property set.
old-location: stream\vram_surface_info_property_s.htm
old-project: stream
ms.assetid: 9bb24ca3-2684-4873-8136-c560f3374310
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: VRAM_SURFACE_INFO_PROPERTY_S, PVRAM_SURFACE_INFO_PROPERTY_S, VRAM_SURFACE_INFO_PROPERTY_S, *PVRAM_SURFACE_INFO_PROPERTY_S
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: VRAM_SURFACE_INFO_PROPERTY_S
req.alt-loc: ksmedia.h
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

# VRAM_SURFACE_INFO_PROPERTY_S structure



## -description
The VRAM_SURFACE_INFO_PROPERTY_S structure describes property items in the KSPROPSETID_VramCapture property set.



## -syntax

````
typedef struct {
  KSPROPERTY         Property;
  PVRAM_SURFACE_INFO pVramSurfaceInfo;
} VRAM_SURFACE_INFO_PROPERTY_S, *PVRAM_SURFACE_INFO_PROPERTY_S;
````


## -struct-fields

### -field Property

This member specifies an initialized <a href="stream.ksproperty">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


### -field pVramSurfaceInfo

This member specifies a pointer to a structure of type <a href="..\ksmedia\ns-ksmedia-vram_surface_info.md">VRAM_SURFACE_INFO</a>.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ksmedia.h (include Ksmedia.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.ksproperty">KSPROPERTY</a>
</dt>
<dt>
<a href="..\ksmedia\ns-ksmedia-vram_surface_info.md">VRAM_SURFACE_INFO</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20VRAM_SURFACE_INFO_PROPERTY_S structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


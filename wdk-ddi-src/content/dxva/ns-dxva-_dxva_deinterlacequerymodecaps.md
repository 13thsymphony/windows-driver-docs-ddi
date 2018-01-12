---
UID: NS:dxva._DXVA_DeinterlaceQueryModeCaps
title: _DXVA_DeinterlaceQueryModeCaps
author: windows-driver-content
description: The DXVA_DeinterlaceQueryModeCaps structure describes a deinterlacing mode.
old-location: display\dxva_deinterlacequerymodecaps.htm
old-project: display
ms.assetid: 4978e4f6-23e3-4381-be4e-550292101013
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXVA_DeinterlaceQueryModeCaps, DXVA_DeinterlaceQueryModeCaps
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXVA_DeinterlaceQueryModeCaps
req.alt-loc: dxva.h
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
req.typenames: DXVA_DeinterlaceQueryModeCaps
---

# _DXVA_DeinterlaceQueryModeCaps structure



## -description
The DXVA_DeinterlaceQueryModeCaps structure describes a deinterlacing mode. 



## -syntax

````
typedef struct _DXVA_DeinterlaceQueryModeCaps {
  DWORD          Size;
  GUID           Guid;
  DXVA_VideoDesc VideoDesc;
} DXVA_DeinterlaceQueryModeCaps;
````


## -struct-fields

### -field Size

Indicates the size of this structure.


### -field Guid

Specifies for which mode of deinterlacing the driver should return capabilities.


### -field VideoDesc

Specifies a <a href="..\dxva\ns-dxva-_dxva_videodesc.md">DXVA_VideoDesc</a> structure that describes the type of video that is to be deinterlaced.


## -remarks
The driver receives the DXVA_DeinterlaceQueryModeCaps structure with all members assigned in a query for capabilities about a particular deinterlacing mode. The driver returns capabilities in a <a href="..\dxva\ns-dxva-_dxva_deinterlacecaps.md">DXVA_DeinterlaceCaps</a> structure.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Dxva.h (include Dxva.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\dxva\ns-dxva-_dxva_deinterlacecaps.md">DXVA_DeinterlaceCaps</a>
</dt>
<dt>
<a href="..\dxva\ns-dxva-_dxva_deinterlacequeryavailablemodes.md">DXVA_DeinterlaceQueryAvailableModes</a>
</dt>
<dt>
<a href="..\dxva\ns-dxva-_dxva_videodesc.md">DXVA_VideoDesc</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_DeinterlaceQueryModeCaps structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


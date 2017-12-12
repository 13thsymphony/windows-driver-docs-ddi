---
UID: NE.d3dumddi._DXVADDI_VIDEOLIGHTING
title: _DXVADDI_VIDEOLIGHTING
author: windows-driver-content
description: The DXVADDI_VIDEOLIGHTING enumeration type contains values that identify lighting conditions for viewing video.
old-location: display\dxvaddi_videolighting.htm
old-project: display
ms.assetid: 2ae1c84e-119a-4649-b3f0-eafbb044dd91
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DXVADDI_VIDEOLIGHTING, DXVADDI_VIDEOLIGHTING
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXVADDI_VIDEOLIGHTING
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
---

# _DXVADDI_VIDEOLIGHTING enumeration



## -description
The DXVADDI_VIDEOLIGHTING enumeration type contains values that identify lighting conditions for viewing video.



## -syntax

````
typedef enum _DXVADDI_VIDEOLIGHTING { 
  DXVADDI_VideoLightingMask      = 0x0F,
  DXVADDI_VideoLighting_Unknown  = 0,
  DXVADDI_VideoLighting_bright   = 1,
  DXVADDI_VideoLighting_office   = 2,
  DXVADDI_VideoLighting_dim      = 3,
  DXVADDI_VideoLighting_dark     = 4
} DXVADDI_VIDEOLIGHTING;
````


## -enum-fields

### -field DXVADDI_VideoLightingMask

The video lighting mask. The first 4 (0x0F) bits of a DWORD can be used to specify video lighting.


### -field DXVADDI_VideoLighting_Unknown

The video lighting condition is not specified. The default is dim.


### -field DXVADDI_VideoLighting_bright

A bright light for viewing video (for example, outside lighting conditions).


### -field DXVADDI_VideoLighting_office

A medium brightness light for viewing video (for example, lighting conditions in home offices).


### -field DXVADDI_VideoLighting_dim

A dim light for viewing video (for example, low-level lighting in a living room while watching television). 


### -field DXVADDI_VideoLighting_dark

Near-darkness for viewing video (for example, movie-theatre lighting).


## -remarks
One of the values of DXVADDI_VIDEOLIGHTING can be specified in the <b>VideoLighting</b> member of the <a href="display.dxvaddi_extendedformat">DXVADDI_EXTENDEDFORMAT</a>.

The video lighting values can be used to alter the gamma to generate a comparable experience in a different lighting condition. 


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
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.dxvaddi_extendedformat">DXVADDI_EXTENDEDFORMAT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVADDI_VIDEOLIGHTING enumeration%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


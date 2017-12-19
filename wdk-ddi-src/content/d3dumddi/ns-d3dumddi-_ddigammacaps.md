---
UID: NS.D3DUMDDI._DDIGAMMACAPS
title: _DDIGAMMACAPS
author: windows-driver-content
description: The DDIGAMMACAPS structure describes gamma-ramp capabilities that the user-mode display driver supports.
old-location: display\ddigammacaps.htm
old-project: display
ms.assetid: 4db605f8-a1ed-4b75-8c72-f4846ae7007e
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DDIGAMMACAPS, DDIGAMMACAPS
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
req.alt-api: DDIGAMMACAPS
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

# _DDIGAMMACAPS structure



## -description
The DDIGAMMACAPS structure describes gamma-ramp capabilities that the user-mode display driver supports.



## -syntax

````
typedef struct _DDIGAMMACAPS {
  UINT GammaCaps;
} DDIGAMMACAPS;
````


## -struct-fields

### -field GammaCaps

[out] A valid bitwise OR of the following capability bits that the driver supports.

<table>
<tr>
<th>Capability bit</th>
<th>Meaning</th>
</tr>
<tr>
<td>
GAMMA_CAP_RGB256x3x16 (0x00000001)

</td>
<td>
Gamma-ramp data is stored as 256 16-bit RGB values.

</td>
</tr>
</table>
 


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
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.d3dddiarg_getcaps">D3DDDIARG_GETCAPS</a>
</dt>
<dt>
<a href="display.d3dddicaps_type">D3DDDICAPS_TYPE</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DDIGAMMACAPS structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


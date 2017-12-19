---
UID: NS.D3DUMDDI._DXVADDI_FREQUENCY
title: _DXVADDI_FREQUENCY
author: windows-driver-content
description: The DXVADDI_FREQUENCY structure describes the video frame rate in Hertz (Hz). For example, NTSC TV is 60000 over 1001.
old-location: display\dxvaddi_frequency.htm
old-project: display
ms.assetid: 5bfb02f6-4482-4260-827f-54c5f74b6b46
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DXVADDI_FREQUENCY, DXVADDI_FREQUENCY
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
req.alt-api: DXVADDI_FREQUENCY
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

# _DXVADDI_FREQUENCY structure



## -description
The DXVADDI_FREQUENCY structure describes the video frame rate in Hertz (Hz). For example, NTSC TV is 60000 over 1001.



## -syntax

````
typedef struct _DXVADDI_FREQUENCY {
  UINT Numerator;
  UINT Denominator;
} DXVADDI_FREQUENCY;
````


## -struct-fields

### -field Numerator

[in] The numerator of the frequency fraction.


### -field Denominator

[in] The denominator of the frequency fraction.


## -remarks
The user-mode display driver must interpret the video frame rate for the following special cases as indicated:

<b>Numerator</b>/<b>Denominator</b> = 0/0 is interpreted as an unknown frequency.

<b>Numerator</b>/<b>Denominator</b> = n/0, where n is any number, is interpreted as invalid.

<b>Numerator</b>/<b>Denominator</b> = 0/n is interpreted as zero frequency.


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
<a href="display.dxvaddi_videodesc">DXVADDI_VIDEODESC</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVADDI_FREQUENCY structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


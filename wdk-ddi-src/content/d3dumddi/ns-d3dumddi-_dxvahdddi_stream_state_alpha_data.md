---
UID: NS.D3DUMDDI._DXVAHDDDI_STREAM_STATE_ALPHA_DATA
title: _DXVAHDDDI_STREAM_STATE_ALPHA_DATA
author: windows-driver-content
description: The DXVAHDDDI_STREAM_STATE_ALPHA_DATA structure describes stream-state data that specifies the alpha blend level per-plane.
old-location: display\dxvahdddi_stream_state_alpha_data.htm
old-project: display
ms.assetid: 0cd14f0c-5b7b-443b-ab37-c455b4accacb
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DXVAHDDDI_STREAM_STATE_ALPHA_DATA, DXVAHDDDI_STREAM_STATE_ALPHA_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_STREAM_STATE_ALPHA_DATA is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXVAHDDDI_STREAM_STATE_ALPHA_DATA
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

# _DXVAHDDDI_STREAM_STATE_ALPHA_DATA structure



## -description
The DXVAHDDDI_STREAM_STATE_ALPHA_DATA structure describes stream-state data that specifies the alpha blend level per-plane. 



## -syntax

````
typedef struct _DXVAHDDDI_STREAM_STATE_ALPHA_DATA {
  BOOL  Enable;
  FLOAT Alpha;
} DXVAHDDDI_STREAM_STATE_ALPHA_DATA;
````


## -struct-fields

### -field Enable

[in] A Boolean value that specifies whether the driver should alpha blend. The default value is <b>FALSE</b>, which indicates that alpha blend is disabled. 


### -field Alpha

[in] A FLOAT value in the 0.0 to 1.0 range that describes the alpha level (that is, the transparency level). The default value is 1.0 for opaque. 


## -remarks
The driver multiplies the alpha value with each source pixel and blends the result with the destination pixel. For example, the driver uses the following values to perform the following calculation:

Cs = source pixel color value

Cd = destination pixel color value

As = per-pixel source alpha value [0.0, 1.0]

Ap = per-plane alpha value [0.0, 1.0]

Ae = per-entry palette alpha value [0.0, 1.0] or 1.0 if the driver did not set the DXVAHDDDI_FEATURE_CAPS_ALPHA_PALETTE value in the <b>FeatureCaps</b> member of the <a href="display.dxvahdddi_vpdevcaps">DXVAHDDDI_VPDEVCAPS</a> structure when the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a> function is called with the D3DDDICAPS_DXVAHD_GETVPDEVCAPS value set.

Cd = Cs * (As * Ap * Ae) + Cd * (1.0 - As * Ap * Ae)

Ad = per-pixel destination alpha value [0.0, 1.0]

The Ad parameter is set with values from the <a href="display.dxvahdddi_alpha_fill_mode">DXVAHDDDI_ALPHA_FILL_MODE</a> enumeration.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
DXVAHDDDI_STREAM_STATE_ALPHA_DATA is supported beginning with the Windows 7 operating system.

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
<a href="display.dxvahdddi_alpha_fill_mode">DXVAHDDDI_ALPHA_FILL_MODE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVAHDDDI_STREAM_STATE_ALPHA_DATA structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


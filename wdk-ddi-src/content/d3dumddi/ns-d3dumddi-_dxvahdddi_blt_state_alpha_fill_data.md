---
UID: NS.D3DUMDDI._DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA
title: _DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA
author: windows-driver-content
description: The DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA structure describes data that specifies the alpha-fill mode of the output.
old-location: display\dxvahdddi_blt_state_alpha_fill_data.htm
old-project: display
ms.assetid: 67fb316e-359f-4bf0-b061-a4b18e359f38
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA, DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA
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

# _DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA structure



## -description
The DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA structure describes data that specifies the alpha-fill mode of the output. 



## -syntax

````
typedef struct _DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA {
  DXVAHDDDI_ALPHA_FILL_MODE Mode;
  UINT                      StreamNumber;
} DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA;
````


## -struct-fields

### -field Mode

[in] A <a href="display.dxvahdddi_alpha_fill_mode">DXVAHDDDI_ALPHA_FILL_MODE</a>-typed value that indicates the type of alpha-fill mode to set. The default value is DXVAHDDDI_ALPHA_FILL_MODE_BACKGROUND, which indicates to fill the output with the alpha value of the background color. 


### -field StreamNumber

[in] A zero-based stream index number. This number must be less than the number, which the driver sets in the <b>MaxStreamStates</b> member of the <a href="display.dxvahdddi_vpdevcaps">DXVAHDDDI_VPDEVCAPS</a> structure. The driver should refer to this number only when the <b>Mode</b> member is set to DXVAHD_ALPHA_FILL_MODE_SOURCE_STREAM. The default value is zero. 


## -remarks
The Direct3D runtime specifies the DXVAHDDDI_BLT_STATE_ALPHA_FILL state in the <b>State</b> member of the <a href="display.d3dddiarg_dxvahd_setvideoprocessbltstate">D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE</a> structure in a call to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_setvideoprocessbltstate.md">SetVideoProcessBltState</a> function only when the output format is a format type with alpha (for example, D3DDDIFMT_A8R8G8B8 from the <a href="display.d3dddiformat">D3DDDIFORMAT</a> enumeration).

The DXVAHD_ALPHA_FILL_MODE_SOURCE_STREAM mode requires the following conditions:

The DXVAHDDDI_BLT_STATE_ALPHA_FILL state only affects alpha within the destination rectangle. The rest of the output remains unchanged. 

If the input format type is without alpha, the source alpha is considered as opaque. 

If the input stream is disabled or unavailable, the output remains unchanged. 


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA is supported beginning with the Windows 7 operating system.

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
<a href="display.d3dddiarg_dxvahd_setvideoprocessbltstate">D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE</a>
</dt>
<dt>
<a href="display.d3dddiformat">D3DDDIFORMAT</a>
</dt>
<dt>
<a href="display.dxvahdddi_alpha_fill_mode">DXVAHDDDI_ALPHA_FILL_MODE</a>
</dt>
<dt>
<a href="display.dxvahdddi_vpdevcaps">DXVAHDDDI_VPDEVCAPS</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_setvideoprocessbltstate.md">SetVideoProcessBltState</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


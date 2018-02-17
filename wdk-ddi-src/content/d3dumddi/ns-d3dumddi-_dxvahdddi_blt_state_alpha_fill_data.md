---
UID: NS:d3dumddi._DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA
title: "_DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA"
author: windows-driver-content
description: The DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA structure describes data that specifies the alpha-fill mode of the output.
old-location: display\dxvahdddi_blt_state_alpha_fill_data.htm
old-project: display
ms.assetid: 67fb316e-359f-4bf0-b061-a4b18e359f38
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dumddi/DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA, DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA structure [Display Devices], DXVA2_Structs_0b64fc90-1ad4-4d38-9fda-68454167b9dd.xml, display.dxvahdddi_blt_state_alpha_fill_data, _DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA, DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dumddi.h
apiname:
-	DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA
product: Windows
targetos: Windows
req.typenames: DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA
---

# _DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA structure
The DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA structure describes data that specifies the alpha-fill mode of the output.

## Syntax
````
typedef struct _DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA {
  DXVAHDDDI_ALPHA_FILL_MODE Mode;
  UINT                      StreamNumber;
} DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA;
````

## Members


`Mode`

[in] A <a href="..\d3dumddi\ne-d3dumddi-_dxvahdddi_alpha_fill_mode.md">DXVAHDDDI_ALPHA_FILL_MODE</a>-typed value that indicates the type of alpha-fill mode to set. The default value is DXVAHDDDI_ALPHA_FILL_MODE_BACKGROUND, which indicates to fill the output with the alpha value of the background color.

`StreamNumber`

[in] A zero-based stream index number. This number must be less than the number, which the driver sets in the <b>MaxStreamStates</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_vpdevcaps.md">DXVAHDDDI_VPDEVCAPS</a> structure. The driver should refer to this number only when the <b>Mode</b> member is set to DXVAHD_ALPHA_FILL_MODE_SOURCE_STREAM. The default value is zero.

## Remarks
The Direct3D runtime specifies the DXVAHDDDI_BLT_STATE_ALPHA_FILL state in the <b>State</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_dxvahd_setvideoprocessbltstate.md">D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE</a> structure in a call to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_setvideoprocessbltstate.md">SetVideoProcessBltState</a> function only when the output format is a format type with alpha (for example, D3DDDIFMT_A8R8G8B8 from the <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a> enumeration).

The DXVAHD_ALPHA_FILL_MODE_SOURCE_STREAM mode requires the following conditions:

<ul>
<li>
The DXVAHDDDI_BLT_STATE_ALPHA_FILL state only affects alpha within the destination rectangle. The rest of the output remains unchanged. 

</li>
<li>
If the input format type is without alpha, the source alpha is considered as opaque. 

</li>
<li>
If the input stream is disabled or unavailable, the output remains unchanged. 

</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA is supported beginning with the Windows 7 operating system. DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA is supported beginning with the Windows 7 operating system. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_setvideoprocessbltstate.md">SetVideoProcessBltState</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_dxvahd_setvideoprocessbltstate.md">D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE</a>



<a href="..\d3dumddi\ne-d3dumddi-_dxvahdddi_alpha_fill_mode.md">DXVAHDDDI_ALPHA_FILL_MODE</a>



<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a>



<a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_vpdevcaps.md">DXVAHDDDI_VPDEVCAPS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
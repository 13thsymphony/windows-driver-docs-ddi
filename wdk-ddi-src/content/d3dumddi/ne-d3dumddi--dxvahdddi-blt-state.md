---
UID: NE.d3dumddi._DXVAHDDDI_BLT_STATE
title: DXVAHDDDI_BLT_STATE
author: windows-driver-content
description: The DXVAHDDDI_BLT_STATE enumeration contains values that identify the bit-block transfer (bitblt) state data for a video processor.
old-location: display\dxvahdddi_blt_state.htm
old-project: display
ms.assetid: c17cf4bd-34f0-4bc6-9efc-2f9a649b5438
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGK_MIRACAST_CHUNK_INFO, DXGK_MIRACAST_CHUNK_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_BLT_STATE is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXVAHDDDI_BLT_STATE
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
req.iface: 
---

# DXVAHDDDI_BLT_STATE enumeration



## -description
<p>The DXVAHDDDI_BLT_STATE enumeration contains values that identify the bit-block transfer (bitblt) state data for a video processor. </p>


## -syntax

````
typedef enum _DXVAHDDDI_BLT_STATE { 
  DXVAHDDDI_BLT_STATE_TARGET_RECT         = 0,
  DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR    = 1,
  DXVAHDDDI_BLT_STATE_OUTPUT_COLOR_SPACE  = 2,
  DXVAHDDDI_BLT_STATE_ALPHA_FILL          = 3,
  DXVAHDDDI_BLT_STATE_CONSTRICTION        = 4,
  DXVAHDDDI_BLT_STATE_PRIVATE             = 1000
} DXVAHDDDI_BLT_STATE;
````


## -enum-fields
<dl>

### -field DXVAHDDDI_BLT_STATE_TARGET_RECT

<dd>
<p>The bitblt state data specifies the target rectangle of the output in a <a href="..\d3dumddi\ns-d3dumddi--dxvahdddi-blt-state-target-rect-data.md">DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA</a> structure. </p>
</dd>

### -field DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR

<dd>
<p>The bitblt state data specifies the background color to fill in the target rectangle of the output in a <a href="..\d3dumddi\ns-d3dumddi--dxvahdddi-blt-state-background-color-data.md">DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR_DATA</a> structure. </p>
</dd>

### -field DXVAHDDDI_BLT_STATE_OUTPUT_COLOR_SPACE

<dd>
<p>The bitblt state data specifies the color space of the output in a <a href="..\d3dumddi\ns-d3dumddi--dxvahdddi-blt-state-output-color-space-data.md">DXVAHDDDI_BLT_STATE_OUTPUT_COLOR_SPACE_DATA</a> structure. </p>
</dd>

### -field DXVAHDDDI_BLT_STATE_ALPHA_FILL

<dd>
<p>The bitblt state data specifies the alpha-fill mode of the output in a <a href="..\d3dumddi\ns-d3dumddi--dxvahdddi-blt-state-alpha-fill-data.md">DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA</a> structure. </p>
</dd>

### -field DXVAHDDDI_BLT_STATE_CONSTRICTION

<dd>
<p>The bitblt state data specifies the down sampling of the output in a <a href="..\d3dumddi\ns-d3dumddi--dxvahdddi-blt-state-constriction-data.md">DXVAHDDDI_BLT_STATE_CONSTRICTION_DATA</a> structure. </p>
</dd>

### -field DXVAHDDDI_BLT_STATE_PRIVATE

<dd>
<p>The bitblt state data specifies the private parameters in a <a href="..\d3dumddi\ns-d3dumddi--dxvahdddi-blt-state-private-data.md">DXVAHDDDI_BLT_STATE_PRIVATE_DATA</a> structure. </p>
</dd>
</dl>

## -remarks
<p>A DXVAHDDDI_BLT_STATE-typed value, which is specified in the <b>State</b> member of the <a href="..\d3dumddi\ns-d3dumddi--d3dddiarg-dxvahd-setvideoprocessbltstate.md">D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE</a> structure in a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-dxvahd-setvideoprocessbltstate.md">SetVideoProcessBltState</a> function, sets the state of a bitblt for a video processor. Bitblt data that corresponds to the supplied DXVAHDDDI_BLT_STATE-typed value is pointed to by the <b>pData</b> member of D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>DXVAHDDDI_BLT_STATE is supported beginning with the Windows 7 operating system.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="..\d3dumddi\ns-d3dumddi--d3dddiarg-dxvahd-setvideoprocessbltstate.md">D3DDDIARG_DXVAHD_SETVIDEOPROCESSBLTSTATE</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi--dxvahdddi-blt-state-alpha-fill-data.md">DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi--dxvahdddi-blt-state-background-color-data.md">DXVAHDDDI_BLT_STATE_BACKGROUND_COLOR_DATA</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi--dxvahdddi-blt-state-constriction-data.md">DXVAHDDDI_BLT_STATE_CONSTRICTION_DATA</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi--dxvahdddi-blt-state-output-color-space-data.md">DXVAHDDDI_BLT_STATE_OUTPUT_COLOR_SPACE_DATA</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi--dxvahdddi-blt-state-private-data.md">DXVAHDDDI_BLT_STATE_PRIVATE_DATA</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi--dxvahdddi-blt-state-target-rect-data.md">DXVAHDDDI_BLT_STATE_TARGET_RECT_DATA</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-dxvahd-setvideoprocessbltstate.md">SetVideoProcessBltState</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVAHDDDI_BLT_STATE enumeration%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

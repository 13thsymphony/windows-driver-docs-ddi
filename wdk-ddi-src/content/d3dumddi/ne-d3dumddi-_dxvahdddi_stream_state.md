---
UID: NE.d3dumddi._DXVAHDDDI_STREAM_STATE
title: _DXVAHDDDI_STREAM_STATE
author: windows-driver-content
description: The DXVAHDDDI_STREAM_STATE enumeration contains values that identify the stream-state data for a video processor.
old-location: display\dxvahdddi_stream_state.htm
old-project: display
ms.assetid: b84e80a3-5d04-4f8d-b469-c56e27e0ad34
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DXVAHDDDI_STREAM_STATE, DXVAHDDDI_STREAM_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_STREAM_STATE is supported starting with Windows 7.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXVAHDDDI_STREAM_STATE
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

# _DXVAHDDDI_STREAM_STATE enumeration



## -description
The DXVAHDDDI_STREAM_STATE enumeration contains values that identify the stream-state data for a video processor.



## -syntax

````
typedef enum _DXVAHDDDI_STREAM_STATE { 
  DXVAHDDDI_STREAM_STATE_FRAME_FORMAT               = 1,
  DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE          = 2,
  DXVAHDDDI_STREAM_STATE_OUTPUT_RATE                = 3,
  DXVAHDDDI_STREAM_STATE_SOURCE_RECT                = 4,
  DXVAHDDDI_STREAM_STATE_DESTINATION_RECT           = 5,
  DXVAHDDDI_STREAM_STATE_ALPHA                      = 6,
  DXVAHDDDI_STREAM_STATE_PALETTE                    = 7,
  DXVAHDDDI_STREAM_STATE_LUMA_KEY                   = 8,
  DXVAHDDDI_STREAM_STATE_ASPECT_RATIO               = 9,
  DXVAHDDDI_STREAM_STATE_ROTATION                   = 10,
  DXVAHDDDI_STREAM_STATE_FILTER_BRIGHTNESS          = 100,
  DXVAHDDDI_STREAM_STATE_FILTER_CONTRAST            = 101,
  DXVAHDDDI_STREAM_STATE_FILTER_HUE                 = 102,
  DXVAHDDDI_STREAM_STATE_FILTER_SATURATION          = 103,
  DXVAHDDDI_STREAM_STATE_FILTER_NOISE_REDUCTION     = 104,
  DXVAHDDDI_STREAM_STATE_FILTER_EDGE_ENHANCEMENT    = 105,
  DXVAHDDDI_STREAM_STATE_FILTER_ANAMORPHIC_SCALING  = 106,
  DXVAHDDDI_STREAM_STATE_PRIVATE                    = 1000
} DXVAHDDDI_STREAM_STATE;
````


## -enum-fields

### -field DXVAHDDDI_STREAM_STATE_FRAME_FORMAT

The stream-state data specifies the frame format of the input in a <a href="display.dxvahdddi_stream_state_frame_format_data">DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA</a> structure. 


### -field DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE

The stream-state data specifies the color space of the input in a <a href="display.dxvahdddi_stream_state_input_color_space_data">DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE_DATA</a> structure. 


### -field DXVAHDDDI_STREAM_STATE_OUTPUT_RATE

The stream-state data specifies the output rate of the input in a <a href="display.dxvahdddi_stream_state_output_rate_data">DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA</a> structure. 


### -field DXVAHDDDI_STREAM_STATE_SOURCE_RECT

The stream-state data specifies the source rectangle of the input in a <a href="display.dxvahdddi_stream_state_source_rect_data">DXVAHDDDI_STREAM_STATE_SOURCE_RECT_DATA</a> structure. 


### -field DXVAHDDDI_STREAM_STATE_DESTINATION_RECT

The stream-state data specifies the destination rectangle in a <a href="display.dxvahdddi_stream_state_destination_rect_data">DXVAHDDDI_STREAM_STATE_DESTINATION_RECT_DATA</a> structure. 


### -field DXVAHDDDI_STREAM_STATE_ALPHA

The stream-state data specifies the alpha blend level per-plane in a <a href="display.dxvahdddi_stream_state_alpha_data">DXVAHDDDI_STREAM_STATE_ALPHA_DATA</a> structure. 


### -field DXVAHDDDI_STREAM_STATE_PALETTE

The stream-state data specifies the palette entries of the input in a <a href="display.dxvahdddi_stream_state_palette_data">DXVAHDDDI_STREAM_STATE_PALETTE_DATA</a> structure. 


### -field DXVAHDDDI_STREAM_STATE_LUMA_KEY

The stream-state data specifies the luma key of the input in a <a href="display.dxvahdddi_stream_state_luma_key_data">DXVAHDDDI_STREAM_STATE_LUMA_KEY_DATA</a> structure. 


### -field DXVAHDDDI_STREAM_STATE_ASPECT_RATIO

The stream-state data specifies the aspect ratio of the input in a <a href="display.dxvahdddi_stream_state_aspect_ratio_data">DXVAHDDDI_STREAM_STATE_ASPECT_RATIO_DATA</a> structure. 


### -field DXVAHDDDI_STREAM_STATE_ROTATION

The stream-state data specifies the  clockwise rotation of the display output surface in a <a href="display.dxvahdddi_stream_state_rotation_data">DXVAHDDDI_STREAM_STATE_ROTATION_DATA</a> structure.

Supported starting with Windows 8.


### -field DXVAHDDDI_STREAM_STATE_FILTER_BRIGHTNESS

The stream-state data specifies the brightness ProcAmp level in a <a href="display.dxvahdddi_stream_state_filter_data">DXVAHDDDI_STREAM_STATE_FILTER_DATA</a> structure. 


### -field DXVAHDDDI_STREAM_STATE_FILTER_CONTRAST

The stream-state data specifies the contrast ProcAmp level in a <a href="display.dxvahdddi_stream_state_filter_data">DXVAHDDDI_STREAM_STATE_FILTER_DATA</a> structure. 


### -field DXVAHDDDI_STREAM_STATE_FILTER_HUE

The stream-state data specifies the hue ProcAmp level in a <a href="display.dxvahdddi_stream_state_filter_data">DXVAHDDDI_STREAM_STATE_FILTER_DATA</a> structure. 


### -field DXVAHDDDI_STREAM_STATE_FILTER_SATURATION

The stream-state data specifies the saturation ProcAmp level in a <a href="display.dxvahdddi_stream_state_filter_data">DXVAHDDDI_STREAM_STATE_FILTER_DATA</a> structure. 


### -field DXVAHDDDI_STREAM_STATE_FILTER_NOISE_REDUCTION

The stream-state data specifies the noise reduction filter level in a <a href="display.dxvahdddi_stream_state_filter_data">DXVAHDDDI_STREAM_STATE_FILTER_DATA</a> structure. 


### -field DXVAHDDDI_STREAM_STATE_FILTER_EDGE_ENHANCEMENT

The stream-state data specifies the edge enhancement filter level in a <a href="display.dxvahdddi_stream_state_filter_data">DXVAHDDDI_STREAM_STATE_FILTER_DATA</a> structure. 


### -field DXVAHDDDI_STREAM_STATE_FILTER_ANAMORPHIC_SCALING

The stream-state data specifies the anamorphic scaling level in a <a href="display.dxvahdddi_stream_state_filter_data">DXVAHDDDI_STREAM_STATE_FILTER_DATA</a> structure. 


### -field DXVAHDDDI_STREAM_STATE_PRIVATE

The stream-state data specifies private parameters in a <a href="display.dxvahdddi_stream_state_private_data">DXVAHDDDI_STREAM_STATE_PRIVATE_DATA</a> structure. 


## -remarks
A DXVAHDDDI_STREAM_STATE-typed value is specified in the <b>State</b> member of the <a href="display.d3dddiarg_dxvahd_setvideoprocessstreamstate">D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE</a> structure in a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_setvideoprocessstreamstate.md">SetVideoProcessStreamState</a> function to set the stream state for a video processor. Stream-state data that corresponds to the supplied DXVAHDDDI_STREAM_STATE-typed value is pointed to by the <b>pData</b> member of D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE. 


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
DXVAHDDDI_STREAM_STATE is supported starting with Windows 7.

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
<a href="display.d3dddiarg_dxvahd_setvideoprocessstreamstate">D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE</a>
</dt>
<dt>
<a href="display.dxvahdddi_stream_state_alpha_data">DXVAHDDDI_STREAM_STATE_ALPHA_DATA</a>
</dt>
<dt>
<a href="display.dxvahdddi_stream_state_aspect_ratio_data">DXVAHDDDI_STREAM_STATE_ASPECT_RATIO_DATA</a>
</dt>
<dt>
<a href="display.dxvahdddi_stream_state_destination_rect_data">DXVAHDDDI_STREAM_STATE_DESTINATION_RECT_DATA</a>
</dt>
<dt>
<a href="display.dxvahdddi_stream_state_filter_data">DXVAHDDDI_STREAM_STATE_FILTER_DATA</a>
</dt>
<dt>
<a href="display.dxvahdddi_stream_state_frame_format_data">DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA</a>
</dt>
<dt>
<a href="display.dxvahdddi_stream_state_input_color_space_data">DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE_DATA</a>
</dt>
<dt>
<a href="display.dxvahdddi_stream_state_luma_key_data">DXVAHDDDI_STREAM_STATE_LUMA_KEY_DATA</a>
</dt>
<dt>
<a href="display.dxvahdddi_stream_state_output_rate_data">DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA</a>
</dt>
<dt>
<a href="display.dxvahdddi_stream_state_palette_data">DXVAHDDDI_STREAM_STATE_PALETTE_DATA</a>
</dt>
<dt>
<a href="display.dxvahdddi_stream_state_private_data">DXVAHDDDI_STREAM_STATE_PRIVATE_DATA</a>
</dt>
<dt>
<a href="display.dxvahdddi_stream_state_rotation_data">DXVAHDDDI_STREAM_STATE_ROTATION_DATA</a>
</dt>
<dt>
<a href="display.dxvahdddi_stream_state_source_rect_data">DXVAHDDDI_STREAM_STATE_SOURCE_RECT_DATA</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_setvideoprocessstreamstate.md">SetVideoProcessStreamState</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVAHDDDI_STREAM_STATE enumeration%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


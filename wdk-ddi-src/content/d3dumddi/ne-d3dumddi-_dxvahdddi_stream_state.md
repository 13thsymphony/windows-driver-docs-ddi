---
UID: NE:d3dumddi._DXVAHDDDI_STREAM_STATE
title: "_DXVAHDDDI_STREAM_STATE"
author: windows-driver-content
description: The DXVAHDDDI_STREAM_STATE enumeration contains values that identify the stream-state data for a video processor.
old-location: display\dxvahdddi_stream_state.htm
old-project: display
ms.assetid: b84e80a3-5d04-4f8d-b469-c56e27e0ad34
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXVAHDDDI_STREAM_STATE_PRIVATE, d3dumddi/DXVAHDDDI_STREAM_STATE_FILTER_CONTRAST, DXVAHDDDI_STREAM_STATE_ASPECT_RATIO, d3dumddi/DXVAHDDDI_STREAM_STATE_PRIVATE, DXVAHDDDI_STREAM_STATE_FILTER_SATURATION, d3dumddi/DXVAHDDDI_STREAM_STATE_PALETTE, d3dumddi/DXVAHDDDI_STREAM_STATE_LUMA_KEY, d3dumddi/DXVAHDDDI_STREAM_STATE_FILTER_NOISE_REDUCTION, d3dumddi/DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE, DXVA2_Structs_7202aa6b-cf67-4d88-aeca-a968e02bcfaf.xml, DXVAHDDDI_STREAM_STATE enumeration [Display Devices], DXVAHDDDI_STREAM_STATE_FILTER_EDGE_ENHANCEMENT, DXVAHDDDI_STREAM_STATE_PALETTE, d3dumddi/DXVAHDDDI_STREAM_STATE_ALPHA, DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE, DXVAHDDDI_STREAM_STATE_ROTATION, DXVAHDDDI_STREAM_STATE_FILTER_CONTRAST, display.dxvahdddi_stream_state, DXVAHDDDI_STREAM_STATE_OUTPUT_RATE, d3dumddi/DXVAHDDDI_STREAM_STATE_OUTPUT_RATE, d3dumddi/DXVAHDDDI_STREAM_STATE_FILTER_BRIGHTNESS, d3dumddi/DXVAHDDDI_STREAM_STATE_ROTATION, DXVAHDDDI_STREAM_STATE_ALPHA, DXVAHDDDI_STREAM_STATE, DXVAHDDDI_STREAM_STATE_DESTINATION_RECT, DXVAHDDDI_STREAM_STATE_FILTER_BRIGHTNESS, d3dumddi/DXVAHDDDI_STREAM_STATE_SOURCE_RECT, d3dumddi/DXVAHDDDI_STREAM_STATE_FRAME_FORMAT, DXVAHDDDI_STREAM_STATE_SOURCE_RECT, d3dumddi/DXVAHDDDI_STREAM_STATE_ASPECT_RATIO, DXVAHDDDI_STREAM_STATE_FRAME_FORMAT, d3dumddi/DXVAHDDDI_STREAM_STATE_FILTER_EDGE_ENHANCEMENT, d3dumddi/DXVAHDDDI_STREAM_STATE_FILTER_ANAMORPHIC_SCALING, _DXVAHDDDI_STREAM_STATE, d3dumddi/DXVAHDDDI_STREAM_STATE, d3dumddi/DXVAHDDDI_STREAM_STATE_DESTINATION_RECT, DXVAHDDDI_STREAM_STATE_LUMA_KEY, d3dumddi/DXVAHDDDI_STREAM_STATE_FILTER_SATURATION, DXVAHDDDI_STREAM_STATE_FILTER_HUE, DXVAHDDDI_STREAM_STATE_FILTER_NOISE_REDUCTION, d3dumddi/DXVAHDDDI_STREAM_STATE_FILTER_HUE, DXVAHDDDI_STREAM_STATE_FILTER_ANAMORPHIC_SCALING
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
-	DXVAHDDDI_STREAM_STATE
product: Windows
targetos: Windows
req.typenames: DXVAHDDDI_STREAM_STATE
---

# _DXVAHDDDI_STREAM_STATE Enumeration
The DXVAHDDDI_STREAM_STATE enumeration contains values that identify the stream-state data for a video processor.

## Syntax
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

## Constants

<table>
            
                <tr>
                    <td>DXVAHDDDI_STREAM_STATE_ALPHA</td>
                    <td>The stream-state data specifies the alpha blend level per-plane in a <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_stream_state_alpha_data.md">DXVAHDDDI_STREAM_STATE_ALPHA_DATA</a> structure.</td>
                </tr>
            
                <tr>
                    <td>DXVAHDDDI_STREAM_STATE_ASPECT_RATIO</td>
                    <td>The stream-state data specifies the aspect ratio of the input in a <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_stream_state_aspect_ratio_data.md">DXVAHDDDI_STREAM_STATE_ASPECT_RATIO_DATA</a> structure.</td>
                </tr>
            
                <tr>
                    <td>DXVAHDDDI_STREAM_STATE_DESTINATION_RECT</td>
                    <td>The stream-state data specifies the destination rectangle in a <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_stream_state_destination_rect_data.md">DXVAHDDDI_STREAM_STATE_DESTINATION_RECT_DATA</a> structure.</td>
                </tr>
            
                <tr>
                    <td>DXVAHDDDI_STREAM_STATE_FILTER_ANAMORPHIC_SCALING</td>
                    <td>The stream-state data specifies the anamorphic scaling level in a <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_stream_state_filter_data.md">DXVAHDDDI_STREAM_STATE_FILTER_DATA</a> structure.</td>
                </tr>
            
                <tr>
                    <td>DXVAHDDDI_STREAM_STATE_FILTER_BRIGHTNESS</td>
                    <td>The stream-state data specifies the brightness ProcAmp level in a <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_stream_state_filter_data.md">DXVAHDDDI_STREAM_STATE_FILTER_DATA</a> structure.</td>
                </tr>
            
                <tr>
                    <td>DXVAHDDDI_STREAM_STATE_FILTER_CONTRAST</td>
                    <td>The stream-state data specifies the contrast ProcAmp level in a <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_stream_state_filter_data.md">DXVAHDDDI_STREAM_STATE_FILTER_DATA</a> structure.</td>
                </tr>
            
                <tr>
                    <td>DXVAHDDDI_STREAM_STATE_FILTER_EDGE_ENHANCEMENT</td>
                    <td>The stream-state data specifies the edge enhancement filter level in a <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_stream_state_filter_data.md">DXVAHDDDI_STREAM_STATE_FILTER_DATA</a> structure.</td>
                </tr>
            
                <tr>
                    <td>DXVAHDDDI_STREAM_STATE_FILTER_HUE</td>
                    <td>The stream-state data specifies the hue ProcAmp level in a <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_stream_state_filter_data.md">DXVAHDDDI_STREAM_STATE_FILTER_DATA</a> structure.</td>
                </tr>
            
                <tr>
                    <td>DXVAHDDDI_STREAM_STATE_FILTER_NOISE_REDUCTION</td>
                    <td>The stream-state data specifies the noise reduction filter level in a <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_stream_state_filter_data.md">DXVAHDDDI_STREAM_STATE_FILTER_DATA</a> structure.</td>
                </tr>
            
                <tr>
                    <td>DXVAHDDDI_STREAM_STATE_FILTER_SATURATION</td>
                    <td>The stream-state data specifies the saturation ProcAmp level in a <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_stream_state_filter_data.md">DXVAHDDDI_STREAM_STATE_FILTER_DATA</a> structure.</td>
                </tr>
            
                <tr>
                    <td>DXVAHDDDI_STREAM_STATE_FRAME_FORMAT</td>
                    <td>The stream-state data specifies the frame format of the input in a <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_stream_state_frame_format_data.md">DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA</a> structure.</td>
                </tr>
            
                <tr>
                    <td>DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE</td>
                    <td>The stream-state data specifies the color space of the input in a <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_stream_state_input_color_space_data.md">DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE_DATA</a> structure.</td>
                </tr>
            
                <tr>
                    <td>DXVAHDDDI_STREAM_STATE_LUMA_KEY</td>
                    <td>The stream-state data specifies the luma key of the input in a <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_stream_state_luma_key_data.md">DXVAHDDDI_STREAM_STATE_LUMA_KEY_DATA</a> structure.</td>
                </tr>
            
                <tr>
                    <td>DXVAHDDDI_STREAM_STATE_OUTPUT_RATE</td>
                    <td>The stream-state data specifies the output rate of the input in a <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_stream_state_output_rate_data.md">DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA</a> structure.</td>
                </tr>
            
                <tr>
                    <td>DXVAHDDDI_STREAM_STATE_PALETTE</td>
                    <td>The stream-state data specifies the palette entries of the input in a <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_stream_state_palette_data.md">DXVAHDDDI_STREAM_STATE_PALETTE_DATA</a> structure.</td>
                </tr>
            
                <tr>
                    <td>DXVAHDDDI_STREAM_STATE_PRIVATE</td>
                    <td>The stream-state data specifies private parameters in a <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_stream_state_private_data.md">DXVAHDDDI_STREAM_STATE_PRIVATE_DATA</a> structure.</td>
                </tr>
            
                <tr>
                    <td>DXVAHDDDI_STREAM_STATE_ROTATION</td>
                    <td>The stream-state data specifies the  clockwise rotation of the display output surface in a <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_stream_state_rotation_data.md">DXVAHDDDI_STREAM_STATE_ROTATION_DATA</a> structure.

Supported starting with Windows 8.</td>
                </tr>
            
                <tr>
                    <td>DXVAHDDDI_STREAM_STATE_SOURCE_RECT</td>
                    <td>The stream-state data specifies the source rectangle of the input in a <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_stream_state_source_rect_data.md">DXVAHDDDI_STREAM_STATE_SOURCE_RECT_DATA</a> structure.</td>
                </tr>
</table>

    ## Remarks

        A DXVAHDDDI_STREAM_STATE-typed value is specified in the <b>State</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_dxvahd_setvideoprocessstreamstate.md">D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE</a> structure in a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_setvideoprocessstreamstate.md">SetVideoProcessStreamState</a> function to set the stream state for a video processor. Stream-state data that corresponds to the supplied DXVAHDDDI_STREAM_STATE-typed value is pointed to by the <b>pData</b> member of D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | DXVAHDDDI_STREAM_STATE is supported starting with Windows 7. DXVAHDDDI_STREAM_STATE is supported starting with Windows 7. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

    ## See Also

        <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_stream_state_frame_format_data.md">DXVAHDDDI_STREAM_STATE_FRAME_FORMAT_DATA</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_setvideoprocessstreamstate.md">SetVideoProcessStreamState</a>

<a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_stream_state_luma_key_data.md">DXVAHDDDI_STREAM_STATE_LUMA_KEY_DATA</a>

<a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_stream_state_filter_data.md">DXVAHDDDI_STREAM_STATE_FILTER_DATA</a>

<a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_stream_state_source_rect_data.md">DXVAHDDDI_STREAM_STATE_SOURCE_RECT_DATA</a>

<a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_stream_state_rotation_data.md">DXVAHDDDI_STREAM_STATE_ROTATION_DATA</a>

<a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_stream_state_private_data.md">DXVAHDDDI_STREAM_STATE_PRIVATE_DATA</a>

<a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_stream_state_output_rate_data.md">DXVAHDDDI_STREAM_STATE_OUTPUT_RATE_DATA</a>

<a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_stream_state_destination_rect_data.md">DXVAHDDDI_STREAM_STATE_DESTINATION_RECT_DATA</a>

<a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_stream_state_aspect_ratio_data.md">DXVAHDDDI_STREAM_STATE_ASPECT_RATIO_DATA</a>

<a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_stream_state_input_color_space_data.md">DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE_DATA</a>

<a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_stream_state_palette_data.md">DXVAHDDDI_STREAM_STATE_PALETTE_DATA</a>

<a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_stream_state_alpha_data.md">DXVAHDDDI_STREAM_STATE_ALPHA_DATA</a>

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_dxvahd_setvideoprocessstreamstate.md">D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVAHDDDI_STREAM_STATE enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
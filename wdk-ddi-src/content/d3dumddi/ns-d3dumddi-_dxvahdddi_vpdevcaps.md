---
UID: NS.D3DUMDDI._DXVAHDDDI_VPDEVCAPS
title: _DXVAHDDDI_VPDEVCAPS
author: windows-driver-content
description: The DXVAHDDDI_VPDEVCAPS structure describes the video processor capabilities that the decode device supports.
old-location: display\dxvahdddi_vpdevcaps.htm
old-project: display
ms.assetid: 25b15c20-e23a-438f-a02e-aedc26498828
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DXVAHDDDI_VPDEVCAPS, DXVAHDDDI_VPDEVCAPS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_VPDEVCAPS is supported starting with Windows 7.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXVAHDDDI_VPDEVCAPS
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

# _DXVAHDDDI_VPDEVCAPS structure



## -description
The DXVAHDDDI_VPDEVCAPS structure describes the video processor capabilities that the decode device supports.



## -syntax

````
typedef struct _DXVAHDDDI_VPDEVCAPS {
  UINT        Reserved;
  UINT        DeviceCaps;
  UINT        FeatureCaps;
  UINT        FilterCaps;
  UINT        InputFormatCaps;
  D3DDDI_POOL InputPool;
  UINT        OutputFormatCount;
  UINT        InputFormatCount;
  UINT        VideoProcessorCount;
  UINT        MaxInputStreams;
  UINT        MaxStreamStates;
} DXVAHDDDI_VPDEVCAPS;
````


## -struct-fields

### -field Reserved

[in] Reserved. Must be zero. 


### -field DeviceCaps

[out] A bitwise OR of the following values from the DXVAHDDDI_DEVICE_CAPS enumeration to indicate device-specific capabilities.




### -field DXVAHDDDI_DEVICE_CAPS_LINEAR_SPACE (0x1)

The driver can blend video content in linear space. Because the video content is traditionally in non-linear space and gamma 2.2 corrected (<a href="http://go.microsoft.com/fwlink/p/?linkid=10112">sRGB</a>), the driver can convert the video content to linear space before performing blending operations to achieve better results.


### -field DXVAHDDDI_DEVICE_CAPS_xvYCC (0x2)

The driver can perform video processing while retaining the extended gamut color when the driver inputs from and outputs to the YCbCr format type.


### -field DXVAHDDDI_DEVICE_CAPS_RGB_RANGE_CONVERSION (0x4)

The driver can perform the range conversion when both input and output are RGB color space but the range is different (for example, the input is full range RGB and the output is limited range RGB). If this value is not set, the driver ignores the RGB range and composes the RGB input stream to the RGB output without changing the range.


### -field DXVAHDDDI_DEVICE_CAPS_YCbCr_MATRIX_CONVERSION (0x8)

The driver can perform the matrix conversion when both input and output are YCbCr color space but the matrix is different (for example, the input is BT.601 and the output is BT.709). If this value is not set, the driver ignores the YCbCr matrix and composes the YCbCr input stream to the YCbCr output without changing the matrix.


### -field DXVAHDDDI_DEVICE_CAPS_NOMINAL_RANGE (0x10)

The video processor can convert between luminance ranges when the input and output use different luminance ranges.

For more information on luminance range, see <a href="display.yuv_format_ranges">YUV format ranges in Windows 8.1</a>.

Supported starting with Windows 8.1.

</dd>
</dl>
The driver determines that the XR_BIAS, FP16, and FP32 formats (wide gamut formats) are in linear space and so can retain the extended gamut color regardless of whether the preceding capability values are set. 


### -field FeatureCaps

[out] A bitwise OR of the following values from the DXVAHDDDI_FEATURE_CAPS enumeration to indicate feature-specific capabilities.




### -field DXVAHDDDI_FEATURE_CAPS_ALPHA_FILL (0x1)

The driver can set the alpha values inside the target rectangle on the output surface as specified for the alpha-fill mode. For more information about this operation, see <a href="display.dxvahdddi_blt_state_alpha_fill_data">DXVAHDDDI_BLT_STATE_ALPHA_FILL_DATA</a>.


### -field DXVAHDDDI_FEATURE_CAPS_CONSTRICTION (0x2)

The driver can down-sample the composed target rectangle. For more information about this operation, see <a href="display.dxvahdddi_blt_state_constriction_data">DXVAHDDDI_BLT_STATE_CONSTRICTION_DATA</a>.


### -field DXVAHDDDI_FEATURE_CAPS_LUMA_KEY (0x4)

The driver can make pixels within a luma-key range transparent. For more information about this operation, see <a href="display.dxvahdddi_stream_state_luma_key_data">DXVAHDDDI_STREAM_STATE_LUMA_KEY_DATA</a>.


### -field DXVAHDDDI_FEATURE_CAPS_ALPHA_PALETTE (0x8)

The driver can apply the alpha value of the palette entry. For more information about alpha blending, see <a href="display.dxvahdddi_stream_state_alpha_data">DXVAHDDDI_STREAM_STATE_ALPHA_DATA</a>.


### -field DXVAHDDDI_FEATURE_CAPS_ROTATION (0x10)

The driver can apply discrete display rotation values to the display output surface. For more information about this operation, see <a href="display.dxvahdddi_stream_state_rotation_data">DXVAHDDDI_STREAM_STATE_ROTATION_DATA</a>.

Supported starting with Windows 8.

</dd>
</dl>

### -field FilterCaps

[out] A bitwise OR of the following values from the DXVAHDDDI_FILTER_CAPS enumeration to indicate filter-specific capabilities.




### -field DXVAHDDDI_FILTER_CAPS_BRIGHTNESS (0x1)

The driver supports brightness ProcAmp.


### -field DXVAHDDDI_FILTER_CAPS_CONTRAST (0x2)

The driver supports contrast ProcAmp.


### -field DXVAHDDDI_FILTER_CAPS_HUE (0x4)

The driver supports hue ProcAmp.


### -field DXVAHDDDI_FILTER_CAPS_SATURATION (0x8)

The driver supports saturation ProcAmp.


### -field DXVAHDDDI_FILTER_CAPS_NOISE_REDUCTION (0x10)

The driver supports noise-reduction filter.


### -field DXVAHDDDI_FILTER_CAPS_EDGE_ENHANCEMENT (0x20)

The driver supports edge-enhancement filter.


### -field DXVAHDDDI_FILTER_CAPS_ANAMORPHIC_SCALING (0x40)

The driver can scale from the source rectangle to the destination rectangle linearly or nonlinearly. If the driver has this capability, it can stretch 4:3 standard video content to 16:9 widescreen.

</dd>
</dl>

### -field InputFormatCaps

[out] A bitwise OR of the following values from the DXVAHDDDI_INPUT_FORMAT_CAPS enumeration to indicate input-format-specific capabilities.




### -field DXVAHDDDI_INPUT_FORMAT_CAPS_RGB_INTERLACED (0x1)

The driver can deinterlace the input stream with RGB format type.


### -field DXVAHDDDI_INPUT_FORMAT_CAPS_RGB_PROCAMP (0x2)

The driver can apply a ProcAmp filter to the input stream with RGB format type.


### -field DXVAHDDDI_INPUT_FORMAT_CAPS_RGB_LUMA_KEY (0x4)

The driver can luma-key the input stream with RGB format type.


### -field DXVAHDDDI_INPUT_FORMAT_CAPS_PALETTE_INTERLACED (0x8)

The driver can deinterlace the input stream with palettized format type.

</dd>
</dl>
The driver can support the preceding capabilities rather than supporting rarely used video processing to the input frames. Because supporting these capabilities requires extra steps in the video processor pipeline, the driver might not support them.

If the driver supports these capabilities, the driver might require a certain color space to perform the processing to the input stream. For example, ProcAmp and the luma keying are performed in YCbCr color space. The driver refers the color space of the stream state to perform the intermediate color conversion.

For example, when the driver sets the <b>RGB_Range</b> and <b>YCbCr_Matrix</b> members of <a href="display.dxvahdddi_stream_state_input_color_space_data">DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE_DATA</a> to 0 and 1 respectively, the driver converts from full range RGB to BT.709 YCbCr before the driver applies ProcAmp, and then converts the input stream back to full range RGB. 


### -field InputPool

[out] A <a href="display.d3dddi_pool">D3DDDI_POOL</a>-typed value that indicates the memory pool from which the input surfaces should be allocated. 


### -field OutputFormatCount

[out] The number of supported output formats. The driver returns an array of <a href="display.d3dddiformat">D3DDDIFORMAT</a> enumeration types for the output formats that the decode device supports when the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a> function is called with the D3DDDICAPS_DXVAHD_GETVPOUTPUTFORMATS value set. 


### -field InputFormatCount

[out] The number of supported input formats. The driver returns an array of <a href="display.d3dddiformat">D3DDDIFORMAT</a> enumeration types for the input formats that the decode device supports when the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a> function is called with the D3DDDICAPS_DXVAHD_GETVPINPUTFORMATS value set. 


### -field VideoProcessorCount

[out] The number of supported video processors. The driver returns an array of <a href="display.dxvahdddi_vpcaps">DXVAHDDDI_VPCAPS</a> structures for the capabilities for each video processor that the decode device supports when the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a> function is called with the D3DDDICAPS_DXVAHD_GETVPCAPS value set. 


### -field MaxInputStreams

[out] The driver can enable the maximum number of input streams at a time. 


### -field MaxStreamStates

[out] The maximum number of stream states. 


## -remarks
The user-mode display driver returns a pointer to a populated DXVAHDDDI_VPDEVCAPS structure in the <b>pData</b> member of the <a href="display.d3dddiarg_getcaps">D3DDDIARG_GETCAPS</a> structure when its <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a> function is called with the D3DDDICAPS_DXVAHD_GETVPDEVCAPS value set in the <b>Type</b> member of D3DDDIARG_GETCAPS.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
DXVAHDDDI_VPDEVCAPS is supported starting with Windows 7.

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
<a href="display.d3dddiformat">D3DDDIFORMAT</a>
</dt>
<dt>
<a href="display.d3dddi_pool">D3DDDI_POOL</a>
</dt>
<dt>
<a href="display.dxvahdddi_vpcaps">DXVAHDDDI_VPCAPS</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVAHDDDI_VPDEVCAPS structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


---
UID: NS.D3DUMDDI._DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE_DATA
title: _DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE_DATA
author: windows-driver-content
description: The DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE_DATA structure describes stream-state data that specifies the color space of the input stream.
old-location: display\dxvahdddi_stream_state_input_color_space_data.htm
old-project: display
ms.assetid: cced26ea-bbb8-4716-b22d-8355b81102c0
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE_DATA, DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE_DATA is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE_DATA
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

# _DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE_DATA structure



## -description
The DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE_DATA structure describes stream-state data that specifies the color space of the input stream. 



## -syntax

````
typedef struct _DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE_DATA {
  union {
    struct {
      UINT Type  :1;
      UINT RGB_Range  :1;
      UINT YCbCr_Matrix  :1;
      UINT YCbCr_xvYCC  :1;
      UINT Nominal_Range  :2;
      UINT Reserved  :26;
    };
    UINT   Value;
  };
} DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE_DATA;
````


## -struct-fields

### -field Type

[in] A UINT value that specifies whether the input stream is video or graphics. The driver can optimize the processing and the filtering based on the stream type. The default value is 0, which indicates a video stream.

Setting this member is equivalent to setting the first bit of the 32-bit <b>Value</b> member (0x00000001). 


### -field RGB_Range

[in] A UINT value that specifies whether the input stream is full range RGB (that is, 0 to 255) or limited range RGB (that is, 16 to 235). The default value is 0, which indicates full range RGB.

Setting this member is equivalent to setting the second bit of the 32-bit <b>Value</b> member (0x00000002). 


### -field YCbCr_Matrix

[in] A UINT value that specifies whether the input stream is BT.601 (for standard digital television) or BT.709 (for high-definition television). The default value is 0, which indicates BT.601.

Setting this member is equivalent to setting the third bit of the 32-bit <b>Value</b> member (0x00000004). 


### -field YCbCr_xvYCC

[in] A UINT value that specifies whether the input stream is conventional YCbCr or extended YCbCr (xvYCC). The default is 0, which indicates conventional YCbCr.

Setting this member is equivalent to setting the fourth bit of the 32-bit <b>Value</b> member (0x00000008). 


### -field Nominal_Range

[in] A UINT value that specifies that the luminance range of YUV data is described by the <a href="display.dxvahdddi_nominal_range">DXVAHDDDI_NOMINAL_RANGE</a> enumeration. The default is zero, which indicates the studio luminance range of 16 to 255, inclusive [16, 235].

For more information on luminance range, see <a href="display.yuv_format_ranges">YUV format ranges in Windows 8.1</a>.

Setting this member is equivalent to setting the fifth and sixth bits of the 32-bit <b>Value</b> member (0x00000030).

Supported starting with Windows 8.1.


### -field Reserved

[in] Reserved. Must be zero.

This member is equivalent to the remaining 26 bits (0xFFFFFFC0) of the 32-bit <b>Value</b> member.


### -field Value

[in] A 32-bit value that describes stream-state data that specifies the color space of the input stream. 


## -remarks
If the driver does not set the DXVAHDDDI_DEVICE_CAPS_xvYCC value in the <b>DeviceCaps</b> member of the <a href="display.dxvahdddi_vpdevcaps">DXVAHDDDI_VPDEVCAPS</a> structure when the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a> function is called with the D3DDDICAPS_DXVAHD_GETVPDEVCAPS value set, the driver ignores the <b>YCbCr_xvYCC</b> member.

Either RGB or YCbCr flags that correspond to the color space of the input format are referred. However, the driver might have to perform the intermediate color space conversion, in which case both RGB and YCbCr flags are referred.

For more information about the intermediate color space conversion, see the <b>InputFormatCaps</b> member of the <a href="display.dxvahdddi_vpdevcaps">DXVAHDDDI_VPDEVCAPS</a> structure.

For more information about color space, see <a href="display.dxvahdddi_blt_state_output_color_space_data">DXVAHDDDI_BLT_STATE_OUTPUT_COLOR_SPACE_DATA</a>.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE_DATA is supported beginning with the Windows 7 operating system.

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
<a href="display.dxvahdddi_blt_state_output_color_space_data">DXVAHDDDI_BLT_STATE_OUTPUT_COLOR_SPACE_DATA</a>
</dt>
<dt>
<a href="display.dxvahdddi_nominal_range">DXVAHDDDI_NOMINAL_RANGE</a>
</dt>
<dt>
<a href="display.dxvahdddi_vpdevcaps">DXVAHDDDI_VPDEVCAPS</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVAHDDDI_STREAM_STATE_INPUT_COLOR_SPACE_DATA structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


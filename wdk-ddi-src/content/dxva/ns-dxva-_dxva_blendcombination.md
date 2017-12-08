---
UID: NS.DXVA._DXVA_BLENDCOMBINATION
title: _DXVA_BlendCombination
author: windows-driver-content
description: The DXVA_BlendCombination structure is sent by the host decoder to the accelerator to specify how a blended picture is created from a source picture and a graphic image with accompanying alpha-blending information.
old-location: display\dxva_blendcombination.htm
old-project: display
ms.assetid: ae711ec5-841d-49cc-a701-1fb6ecaa9a66
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _DXVA_BlendCombination, *LPDXVA_BlendCombination, DXVA_BlendCombination
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXVA_BlendCombination
req.alt-loc: dxva.h
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

# _DXVA_BlendCombination structure



## -description
The DXVA_BlendCombination structure is sent by the host decoder to the accelerator to specify how a blended picture is created from a source picture and a graphic image with accompanying alpha-blending information.


## -syntax

````
typedef struct _DXVA_BlendCombination {
  WORD             wPictureSourceIndex;
  WORD             wBlendedDestinationIndex;
  RECT             PictureSourceRect16thPel;
  RECT             PictureDestinationRect;
  RECT             GraphicSourceRect;
  RECT             GraphicDestinationRect;
  WORD             wBlendDelay;
  BYTE             bBlendOn;
  BYTE             bWholePlaneAlpha;
  DXVA_AYUVsample2 OutsideYUVcolor;
} DXVA_BlendCombination, *LPDXVA_BlendCombination;
````


## -struct-fields

### -field wPictureSourceIndex

Specifies the uncompressed surface index, as defined by the contents of the DWORD pointed to by the <b>lpInputData</b> member of <a href="display.dd_beginmocompframedata">DD_BEGINMOCOMPFRAMEDATA</a> in a prior call to <a href="display.ddmocompbeginframe">DdMoCompBeginFrame</a>, of the picture to be combined with the graphic. This value is 0xFFFF if back-end hardware alpha blending is in use (when the <b>bConfigBlendType</b> member of <a href="display.dxva_configalphacombine">DXVA_ConfigAlphaCombine</a> is 1).

### -field wBlendedDestinationIndex

Specifies the uncompressed surface index, as defined by the contents of the DWORD pointed to by the <b>lpInputData</b> member of DD_BEGINMOCOMPFRAMEDATA in a prior call to <b>DdMoCompBeginFrame</b>, of the combined picture to be created. This value is 0xFFFF if back-end hardware alpha blending is in use (when the <b>bConfigBlendType</b> member of DXVA_ConfigAlphaCombine is 1). 
This value cannot be equal to <b>wPictureSourceIndex</b> unless back-end hardware alpha blending is in use.

### -field PictureSourceRect16thPel

Specifies the area of the source picture to be combined with the graphic image as a <a href="display.rect">RECT</a> structure. Dimensions are specified in units of one-sixteenth of the distance between sample values of the luminance component. (In other words, the members in the RECT structure are fixed-point representations that have 28 bits before the binary point and 4 bits after the binary point.) This one-sixteenth sample accuracy allows <b>PictureSourceRect16thPel</b> to contain the same accuracy as the <i>frame_centre_horizontal_offset</i> and <i>frame_centre_vertical_offset</i> pan-scan variables in MPEG-2 video.
If the <b>bConfigPictureResizing</b> member of DXVA_ConfigAlphaCombine is zero, all dimensions in <b>PictureSourceRect16thPel</b> must be integer multiples of 16.

### -field PictureDestinationRect

Specifies the area of the destination picture as a RECT structure. This will contain the area defined for the source picture by <b>PictureSourceRect16thPel</b>.
If the <b>bConfigPictureResizing</b> member of <a href="display.dxva_configalphacombine">DXVA_ConfigAlphaCombine</a> is zero, the area specified by <b>PictureDestinationRect</b> must have the same width and height as the area specified by <b>PictureSourceRect16thPel</b>. If <b>PictureDestinationRect</b> differs in size from <b>PictureSourceRect16thPel</b>, the resampling method to be applied is not specified, but must have a quality that is at least equivalent to that of bilinear resampling.

### -field GraphicSourceRect

Specifies the area of the source graphic image as a <a href="display.rect">RECT</a> structure. This area is combined with the part of the source picture specified by <b>PictureSourceRect16thPel</b> to create the alpha-blended picture.

### -field GraphicDestinationRect

Specifies the area of the destination graphic image as a <a href="display.rect">RECT</a> structure.
If the <b>bConfigGraphicResizing</b> member of DXVA_ConfigAlphaCombine is zero, the destination picture must have the same width and height as the area specified by <b>GraphicSourceRect</b>. If <b>GraphicDestinationRect</b> differs in size from <b>GraphicSourceRect</b>, the resampling method to be applied to the graphic image is not specified. However, the resampling method used should have a quality that is at least equivalent to a bilinear resampling of an AYUV surface that represents the blending information.

### -field wBlendDelay

Specifies the number of milliseconds of delay prior to the blending combination going into effect. If back-end hardware blending is in use (for example, if the <b>bConfigBlendType</b> member of <a href="display.dxva_configalphacombine">DXVA_ConfigAlphaCombine</a> is 1), <b>wBlendDelay</b> contains the number of milliseconds of delay prior to the blending combination going into effect. If front-end blending is in use, this member has no meaning and must be zero.

### -field bBlendOn

Specifies when a blending combination operation starts and stops. If back-end hardware blending is in use, blending is applied from the time specified in a blending combination operation (with <b>bBlendOn</b> equal to 1) until the execution time of a new blending combination (with <b>bBlendOn</b> equal to 1), or until the blending is disabled by a blending combination operation (with <b>bBlendOn</b> equal to zero). If back-end hardware blending is in use and <b>bBlendOn</b> is zero, the only other value in the alpha-blend combination buffer that has meaning is <b>wBlendDelay</b>. If front-end blending is in use, this member has no meaning and must be zero .

### -field bWholePlaneAlpha

Contains an opacity multiplier for the alpha channel of the graphic image. The value zero indicates that the graphic image is transparent (so that the graphic content has no effect on the resulting blended picture). The value 255 indicates that the graphic image uses its full sample opacity. If <b>bWholePlaneAlpha</b> is not equal to zero, the blend specified is to multiply the opacity of each location in the graphic content by (<b>bWholePlaneAlpha</b>+1)/256. For a zero value of <b>bWholePlaneAlpha</b>, the blend to use is the opacity specified in the graphic image without alteration. This must be equal to 255 if the <b>bConfigWholePlaneAlpha</b> member of <a href="display.dxva_configalphacombine">DXVA_ConfigAlphaCombine</a> is zero.

### -field OutsideYUVcolor

Indicates whether areas outside of the <b>PictureDestinationRect</b> use a constant color for blending. If so, this member specifies that color constant. The <b>OutsideYUVcolor</b> member is defined as a <a href="display.dxva_ayuvsample2">DXVA_AYUVsample2</a> structure. See the <b>Remarks</b> section for more information.

## -remarks
In the event that the source and destination pictures are not in 4:4:4 format, every second sample of the graphic blending information (for example, the first, third, or fifth) is applied to the subsampled source chrominance information in the vertical or horizontal direction as needed to produce the blended result.

The following sections show the restrictions placed on the <b>left</b>, <b>right</b>, <b>top</b>, and <b>bottom</b> members of the RECT structure.

The following restrictions apply to the <a href="display.rect">RECT</a> dimensions of <b>PictureSourceRect16thPel</b>:

<b>left</b> and <b>top</b> must be greater than or equal to zero.

<b>right</b> and <b>bottom</b> must be greater than or equal to <b>left</b> and <b>top</b>, respectively.

If <b>right</b> is equal to <b>left</b> or <b>top</b> is equal to <b>bottom</b>, all the RECT members must have the value zero indicating that the source picture is not used. This case is allowed only if the <b>bConfigOnlyUsePicDestRectArea</b> member of <a href="display.dxva_configalphacombine">DXVA_ConfigAlphaCombine</a> is zero.

<b>right</b> and <b>bottom</b> must not exceed 16 times the allocated width and height, respectively, of the uncompressed source picture surface.

For example, if <b>PictureSourceRect16thPel</b> is used to select an entire MPEG-2 decoded picture, the <b>PictureSourceRect16thPel</b> values can be computed as follows:

<b>left</b> = 0

<b>top</b> = 0

<b>right</b> = 16 X <i>horizontal_size</i>

<b>bottom</b> = 16 X <i>vertical_size</i>

The following restrictions apply to the <a href="display.rect">RECT</a> dimensions for <b>PictureDestinationRect</b>:

If <b>right</b> is equal to <b>left</b> or <b>top</b> is equal to <b>bottom</b> (only allowed if the <b>bConfigOnlyUsePicDestRectArea</b> member of <a href="display.dxva_configalphacombine">DXVA_ConfigAlphaCombine</a> is zero), all of the <a href="display.rect">RECT</a> members must have the value zero and <b>PictureSourceRect16thPel</b> must also specify all values having the value zero.

If the <b>bConfigBlendType</b> member of DXVA_ConfigAlphaCombine is zero, <b>right</b> and <b>bottom</b> must not exceed the allocated width and height, respectively, of the uncompressed destination picture surface.

If the <b>bConfigBlendType</b> member of DXVA_ConfigAlphaCombine is 1, <b>right</b> and <b>bottom</b> must not exceed the allocated width and height, respectively, of the source graphic surface.

If alpha-blend data loading uses the <b>bConfigDataType</b> member of <a href="display.dxva_configalphaload">DXVA_ConfigAlphaLoad</a> with a value of 2, the following restrictions apply to the <a href="display.rect">RECT</a> dimensions of <b>GraphicSourceRect</b>:

<b>top </b>and <b>left </b>must be zero.

<b>right</b> must be equal to the End X-coordinate minus the Start X-coordinate of the last preceding DVD SET_DAREA DCCMD, plus 1, to adjust for the differing rectangle interpretations as described in the following note in the RECT Structure Restrictions for <b>GraphicDestinationRect</b> section.

<b>bottom</b> must be equal to the End Y-coordinate minus the Start Y-coordinate of the last preceding DVD SET_DAREA DCCMD, plus 1, to adjust for the differing rectangle interpretations.

If alpha-blend data loading does not use the <b>bConfigDataType</b> member of DXVA_ConfigAlphaLoad with a value of 2, the following restrictions apply to the RECT dimensions of <b>GraphicSourceRect</b>:

<b>right </b>and <b>bottom</b> must be greater than or equal to <b>left</b> and <b>top</b>, respectively.

If <b>right</b> is equal to <b>left</b> or <b>top</b> is equal to <b>bottom</b>, all the RECT members must have the value zero, indicating no use of the graphic picture. 

<b>right</b> and <b>bottom</b> must not exceed the allocated width and height, respectively, of the graphic source image. The allocated width and height are defined as 720 and 576 samples, respectively, when the <b>bConfigDataType</b> member of DXVA_ConfigAlphaLoad equals 2.

The following restrictions apply to the <a href="display.rect">RECT</a> dimensions of <b>GraphicDestinationRect</b>:

<b>right</b> and <b>bottom</b> must be greater than or equal to <b>left</b> and <b>top</b>, respectively. If <b>right</b> is equal to <b>left</b> or <b>top</b> is equal to <b>bottom</b>, then all these members of the RECT structure must have the value zero and <b>GraphicSourceRect</b> must also specify that all its members have the value zero.

If the <b>bConfigBlendType</b> member of <a href="display.dxva_configalphacombine">DXVA_ConfigAlphaCombine</a> equals zero, <b>right</b> and <b>bottom</b> must not exceed the allocated width and height, respectively, of the uncompressed destination picture surface.

If the <b>bConfigBlendType</b> member of DXVA_ConfigAlphaCombine equals 1, <b>right</b> and <b>bottom</b> must not exceed the allocated width and height, respectively, of the source graphic image.

If alpha-blend data loading uses the <b>bConfigDataType</b> member of DXVA_ConfigAlphaCombine with a value of 2 and the <b>bConfigGraphicResizing</b> member of DXVA_ConfigAlphaCombine with a value of zero, the following additional restrictions on <b>GraphicDestinationRect</b> dimensions apply:

<b>top</b> must be equal to the Start Y-coordinate of the last preceding DVD SET_DAREA DCCMD.

<b>left</b> must be equal to either the Start X-coordinate of the last preceding DVD SET_DAREA DCCMD or to that value minus 8. For more information, see <a href="https://msdn.microsoft.com/df335e5e-4f7c-440a-88ef-00f6e0f916e2">DVD 704-Wide Non-Pan-Scan Example</a> and <a href="https://msdn.microsoft.com/22047c8e-30e3-4204-9f7d-b8b97be668ae">DVD 352-Wide Example</a>.

<b>right</b> must be equal to the value of <b>left</b>, plus the End X-coordinate minus the Start X-coordinate of the last preceding DVD SET_DAREA DCCMD, plus 1, to adjust for the differing rectangle interpretations described in the following note.

<b>bottom</b> must be equal to the value of <b>top</b> plus the End Y-coordinate minus the Start Y-coordinate of the last preceding DVD SET_DAREA DCCMD, plus 1, to adjust for the differing rectangle interpretations described in the following note.

The values for the <b>OutsideYUVcolor</b> structure are as follows:

The value of <b>OutsideYUVcolor.bSampleAlpha8</b> must be 255 if the areas outside of the <b>PictureDestinationRect</b> are generated as a constant color to use for blending.

All other values for <b>OutsideYUVcolor.bSampleAlpha8</b> are reserved for future use.

The value of <b>OutsideYUVcolor.bSampleAlpha8</b> must be zero if the <b>bConfigStayInPicDestRectArea</b> member of the DXVA_ConfigAlphaCombine structure equals 1.

If <b>OutsideYUVcolor.bSampleAlpha8</b> is zero, the only area of the destination surface that is affected by the blend is the part within the <b>PictureDestinationRect</b>.

If <b>OutsideYUVcolor.bSampleAlpha8</b> is 255, any area of the destination surface that is outside of <b>PictureDestinationRect</b> but within <b>GraphicDestinationRect</b>, is generated by blending the graphic with the color specified in the nonalpha members of <b>OutsideYUVcolor</b>. In this case, the entire allocated area of the destination surface that falls outside of both <b>PictureDestinationRect</b> and <b>GraphicDestinationRect</b> is set to the color specified in the nonalpha members of <b>OutsideYUVcolor</b>. If the <b>bConfigBlendType</b> member of the <a href="display.dxva_configalphacombine">DXVA_ConfigAlphaCombine</a> structure is 1, the <b>OutsideYUVcolor</b> members are set to indicate blending with black by specifying <b>bSampleAlpha8</b> = 255, <b>bY_Value</b> = 16, and <b>bCbValue</b> = <b>bCrValue</b> = 128.

When the <b>bConfigBlendType</b> member of the DXVA_ConfigAlphaCombine structure is 1  (back-end hardware blend), blending operations may differ somewhat from those described in this reference. Some resizing parameters used to map a video picture from a source picture to a destination picture size may be applied in a modified manner to map the graphic image to its proper location relative to the source picture. However, the blended result will be equivalent to the blended result obtained by the alpha-blend combination commands in this reference.

## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Dxva.h (include Dxva.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.dxva_configalphacombine">DXVA_ConfigAlphaCombine</a>
</dt>
<dt>
<a href="display.dd_beginmocompframedata">DD_BEGINMOCOMPFRAMEDATA</a>
</dt>
<dt>
<a href="display.dxva_ayuvsample2">DXVA_AYUVsample2</a>
</dt>
<dt>
<a href="display.rect">RECT</a>
</dt>
<dt>
<a href="display.ddmocompbeginframe">DdMoCompBeginFrame</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_BlendCombination structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

---
UID: NS.d3dumddi._DXVADDI_CONFIGPICTUREDECODE
title: DXVADDI_CONFIGPICTUREDECODE
author: windows-driver-content
description: The DXVADDI_CONFIGPICTUREDECODE structure describes the configuration for compressed picture decoding.
old-location: display\dxvaddi_configpicturedecode.htm
old-project: display
ms.assetid: 3305b892-6785-4412-9b9e-86561c83764a
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXVADDI_CONFIGPICTUREDECODE, DXVADDI_CONFIGPICTUREDECODE
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
req.alt-api: DXVADDI_CONFIGPICTUREDECODE
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

# DXVADDI_CONFIGPICTUREDECODE structure



## -description
<p>The DXVADDI_CONFIGPICTUREDECODE structure describes the configuration for compressed picture decoding. </p>


## -syntax

````
typedef struct _DXVADDI_CONFIGPICTUREDECODE {
  GUID   guidConfigBitstreamEncryption;
  GUID   guidConfigMBcontrolEncryption;
  GUID   guidConfigResidDiffEncryption;
  UINT   ConfigBitstreamRaw;
  UINT   ConfigMBcontrolRasterOrder;
  UINT   ConfigResidDiffHost;
  UINT   ConfigSpatialResid8;
  UINT   ConfigResid8Subtraction;
  UINT   ConfigSpatialHost8or9Clipping;
  UINT   ConfigSpatialResidInterleaved;
  UINT   ConfigIntraResidUnsigned;
  UINT   ConfigResidDiffAccelerator;
  UINT   ConfigHostInverseScan;
  UINT   ConfigSpecificIDCT;
  UINT   Config4GroupedCoefs;
  USHORT ConfigMinRenderTargetBuffCount;
  USHORT ConfigDecoderSpecific;
} DXVADDI_CONFIGPICTUREDECODE;
````


## -struct-fields
<dl>

### -field <b>guidConfigBitstreamEncryption</b>

<dd>
<p>[in] The encryption GUID for configuring a bitstream. </p>
</dd>

### -field <b>guidConfigMBcontrolEncryption</b>

<dd>
<p>[in] The encryption GUID for configuring macroblock control. </p>
</dd>

### -field <b>guidConfigResidDiffEncryption</b>

<dd>
<p>[in] The encryption GUID for configuring residual difference decoding.</p>
</dd>

### -field <b>ConfigBitstreamRaw</b>

<dd>
<p>[in] The bitstream processing indicator. A value of 1 in this member indicates that picture data is sent in bitstream buffers as raw bitstream content. A value of zero indicates that picture data is sent by using macroblock control command buffers. </p>
<p>Set this member to zero if the <b>ConfigResidDiffHost</b> or <b>ConfigResidDiffAccelerator</b> member is 1. A value of zero in <b>ConfigBitstreamRaw </b>is the basic level of support. The value of 1 is preferred. </p>
</dd>

### -field <b>ConfigMBcontrolRasterOrder</b>

<dd>
<p>[in] A UINT value that specifies whether macroblock control commands are in raster scan order or in arbitrary order. A value of 1 in this member specifies that the macroblock control commands within each macroblock control command buffer are in raster scan order. A value of zero indicates arbitrary order. A driver can restrict support to raster scan order; however, a driver should support both arbitrary and raster scan order.</p>
</dd>

### -field <b>ConfigResidDiffHost</b>

<dd>
<p>[in] The host residual difference configuration. A value of 1 in this member specifies that some residual difference decoding data is possibly sent as blocks in the spatial domain from the host. A value of zero specifies that spatial domain data is not sent. Set this member to zero if the <b>ConfigBitstreamRaw</b> member is 1. An accelerator should support both zero and 1.</p>
</dd>

### -field <b>ConfigSpatialResid8</b>

<dd>
<p>[in] The word size that is used to represent residual difference spatial-domain blocks for predicted (nonintra) pictures when using host-based residual difference decoding (that is, when the <b>ConfigResidDiffHost</b> member is set to 1).</p>
<p>If <b>ConfigSpatialResid8</b> is 1 and <b>ConfigResidDiffHost</b> is 1, the host sends residual difference spatial-domain blocks for nonintra macroblocks that use 8-bit signed samples and for intra macroblocks in predicted (nonintra) pictures in a format that depends on the <b>ConfigIntraResidUnsigned</b> member as follows:</p>
<ul>
<li>
<p>If <b>ConfigIntraResidUnsigned</b> is zero, spatial-domain blocks for intra macroblocks are sent as 8-bit signed integer values that are relative to a constant reference value of 128.</p>
</li>
<li>
<p>If <b>ConfigIntraResidUnsigned</b> is 1, spatial-domain blocks for intra macroblocks are sent as 8-bit unsigned integer values that are relative to a constant reference value of zero.</p>
</li>
</ul>
<p>If <b>ConfigSpatialResid8</b> is zero and <b>ConfigResidDiffHost</b> is 1, the host sends residual difference spatial-domain blocks of data for nonintra macroblocks that use 16-bit signed samples and for intra macroblocks in predicted (nonintra) pictures in a format that depends on <b>ConfigIntraResidUnsigned</b> as follows:</p>
<ul>
<li>
<p>If <b>ConfigIntraResidUnsigned</b> is zero, spatial domain blocks for intra macroblocks are sent as 16-bit signed integer values that are relative to a constant reference value of 2<sup>(BPP-1)</sup>, where <i>BPP</i> is the number of bits per sample for the uncompressed video (generally a value of 8).</p>
</li>
<li>
<p>If <b>ConfigIntraResidUnsigned</b> is 1, spatial domain blocks for intra macroblocks are sent as 16-bit unsigned integer values that are relative to a constant reference value of zero.</p>
</li>
</ul>
<p><b>ConfigSpatialResid8</b> must be zero if <b>ConfigResidDiffHost</b> is zero. If <b>ConfigResidDiffHost</b> is 1, <b>ConfigSpatialResid8</b> can be any value.</p>
<div class="alert"><b>Note</b>    For <a href="wdkgloss.i#wdkgloss.intra_picture#wdkgloss.intra_picture"><i>intra pictures</i></a> with <i>BPP</i> equal to 8, spatial-domain blocks must be sent by using 8-bit samples. For intra pictures with <i>BPP</i> greater than 8, spatial-domain blocks must be sent by using 16-bit samples. <p class="note">If <b>ConfigIntraResidUnsigned</b> is zero, these samples are sent as signed integer values that are relative to a constant reference value of 2<sup>(BPP-1)</sup>. If <b>ConfigIntraResidUnsigned</b> is 1, these samples are sent as unsigned integer values that are relative to a constant reference value of zero.</p>
</div>
<div> </div>
</dd>

### -field <b>ConfigResid8Subtraction</b>

<dd>
<p>[in] A UINT value that specifies whether 8-bit difference overflow blocks are subtracted or added. If this member is set to 1, 8-bit difference overflow blocks are subtracted rather than added. This member must be zero unless <b>ConfigSpatialResid8</b> is 1. If <b>ConfigSpatialResid8</b> is 1, the preferred value for <b>ConfigResid8Subtraction</b> is 1. The ability to subtract differences rather than to add them enables 8-bit difference decoding to be fully compliant with the range from -255 through +255 of values that are required in video decoder specifications. This ability enables full compliance because +255 cannot be represented as the addition of two signed 8-bit numbers but any number in the range from -255 through +255 can be represented as the difference between two signed 8-bit numbers (+255 is equal to +127 minus âˆ’128).</p>
</dd>

### -field <b>ConfigSpatialHost8or9Clipping</b>

<dd>
<p>[in] A UINT value that specifies whether clipping is performed by the host. If this member set to 1, spatial-domain blocks for intra macroblocks are clipped to an 8-bit range on the host and spatial-domain blocks for nonintra macroblocks are clipped to a 9-bit range on the host. A value of zero indicates that no such clipping is performed by the host. This member must be zero unless <b>ConfigSpatialResid8</b> is set to zero and <b>ConfigResidDiffHost</b> is set to 1. The preferred value for <b>ConfigSpatialHost8or9Clipping</b> is zero.</p>
</dd>

### -field <b>ConfigSpatialResidInterleaved</b>

<dd>
<p>[in] A UINT value that specifies whether spatial-domain residual difference data is sent in a chrominance-interleaved form. If this member is set to 1, any spatial-domain residual difference data is sent in a chrominance-interleaved form that matches the YUV format chrominance interleaving pattern. This member must be zero unless <b>ConfigResidDiffHost</b> is 1 and the YUV format is NV12 or NV21. The preferred value for <b>ConfigSpatialResidInterleaved</b> is zero.</p>
</dd>

### -field <b>ConfigIntraResidUnsigned</b>

<dd>
<p>[in] The method of representation of spatial-domain blocks of residual difference data for intra blocks when using host-based difference decoding (that is, when the <b>ConfigResidDiffHost</b> member is equal to 1).</p>
<p>If <b>ConfigIntraResidUnsigned</b> is set to zero and <b>ConfigResidDiffHost</b> is set to 1, spatial-domain residual difference data blocks for intra macroblocks are sent as follows:</p>
<ul>
<li>
<p>In a nonintra picture if the <b>ConfigSpatialResid8</b> member is zero, the spatial-domain residual difference data blocks for intra macroblocks are sent as 16-bit signed integer values that are relative to a constant reference value of 2<sup>(BPP-1)</sup>, where <i>BPP</i> is the number of bits per sample for the uncompressed video (generally a value of 8).</p>
</li>
<li>
<p>In a nonintra picture if <b>ConfigSpatialResid8</b> is 1 and in an intra picture if <i>BPP</i> is equal to 8 (regardless of the value of <b>ConfigSpatialResid8</b>), the spatial-domain residual difference data blocks for intra macroblocks are sent as 8-bit signed integer values that are relative to a constant reference value of 128.</p>
</li>
</ul>
<p>If <b>ConfigIntraResidUnsigned</b> is set to 1 and <b>ConfigResidDiffHost</b> is set to 1, spatial-domain residual difference data blocks for intra macroblocks are sent as follows:</p>
<ul>
<li>
<p>In a nonintra picture if <b>ConfigSpatialResid8</b> is zero, the spatial-domain residual difference data blocks for intra macroblocks are sent as 16-bit unsigned integer values that are relative to a constant reference value of zero.</p>
</li>
<li>
<p>In a nonintra picture if <b>ConfigSpatialResid8</b> is 1 and in an intra picture if <i>BPP</i> is equal to 8 (regardless of the value of <b>ConfigSpatialResid8</b>), the spatial-domain residual difference data blocks for intra macroblocks are sent as 8-bit unsigned integer values that are relative to a constant reference value of zero.</p>
</li>
</ul>
<p><b>ConfigIntraResidUnsigned</b> must be zero unless <b>ConfigResidDiffHost</b> is 1. The preferred value for <b>ConfigIntraResidUnsigned</b> is zero.</p>
</dd>

### -field <b>ConfigResidDiffAccelerator</b>

<dd>
<p>[in] The accelerator residual difference configuration. A value of 1 in this member indicates that transform-domain blocks of coefficient data can be sent from the host for accelerator-based IDCT. A value of zero indicates that accelerator-based IDCT is not used. </p>
<p>If both the <b>ConfigResidDiffHost</b> member and <b>ConfigResidDiffAccelerator</b> are 1, some residual difference decoding is performed on the host and some on the accelerator, as indicated by macroblock-level control commands. <b>ConfigResidDiffAccelerator</b> must be zero if the <b>bConfigBitstreamRaw</b> member is 1. </p>
<p>The preferred value for <b>ConfigResidDiffAccelerator</b> is 1.</p>
<p>If <b>ConfigResidDiffAccelerator</b> and <b>ConfigResidDiffHost</b> are set to 1, residual difference decoding can be shared between the host and accelerator on a macroblock basis. This sharing is an even higher level of accelerator capability than when <b>ConfigResidDiffAccelerator</b> is set to 1 and <b>ConfigResidDiffHost</b> is set to zero.</p>
</dd>

### -field <b>ConfigHostInverseScan</b>

<dd>
<p>[in] A UINT value that specifies whether the inverse scan for transform-domain block processing is performed on the host or the accelerator. A value of 1 in this member indicates that the inverse scan for transform-domain block processing is performed on the host, and absolute indexes are sent instead for any transform coefficients. A value of zero indicates that inverse scan is performed on the accelerator. <b>ConfigHostInverseScan</b> must be zero if <b>ConfigResidDiffAccelerator</b> is zero or if the <b>Config4GroupedCoefs</b> member is 1.</p>
<p>The preferred value for <b>ConfigHostInverseScan</b> is 1 if <b>ConfigResidDiffAccelerator</b> is 1.</p>
</dd>

### -field <b>ConfigSpecificIDCT</b>

<dd>
<p>[in] A UINT value that specifies the use of a specific <a href="wdkgloss.i#wdkgloss.idct#wdkgloss.idct"><i>IDCT</i></a> method for off-host IDCT. A value of 1 in this member indicates the use of the IDCT that is specified in Annex W of ITU-T Recommendation H.263, which you can learn about from the <a href="http://go.microsoft.com/fwlink/p/?linkid=8741">International Telecommunication Union</a> website. A value of zero indicates that any compliant IDCT can be used for off-host IDCT. (Values other than zero and 1 are reserved.)</p>
<p><b>ConfigSpecificIDCT</b> must be zero if <b>ConfigResidDiffAccelerator</b> is zero, which indicates host-based residual difference decoding.</p>
<div class="alert"><b>Note</b>  <b>ConfigSpecificIDCT</b> must not be set to 1 for use with MPEG-2 video. </div>
<div> </div>
</dd>

### -field <b>Config4GroupedCoefs</b>

<dd>
<p>[in] A UINT value that specifies how transform coefficients for off-host IDCT are sent. A value of 1 in this member indicates that transform coefficients for off-host IDCT are sent by using the <a href="..\dxva\ns-dxva--dxva-tcoef4group.md">DXVA_TCoef4Group</a> structure rather than the <a href="..\dxva\ns-dxva--dxva-tcoefsingle.md">DXVA_TCoefSingle</a> structure. <b>Config4GroupedCoefs</b> is zero if <b>ConfigResidDiffAccelerator</b> is zero or if <b>ConfigHostInverseScan</b> is 1.</p>
<p>The preferred value for <b>Config4GroupedCoefs</b> is zero if <b>ConfigResidDiffAccelerator</b> is 1.</p>
</dd>

### -field <b>ConfigMinRenderTargetBuffCount</b>

<dd>
<p>[in] A USHORT value that specifies the minimum number of render target buffers.</p>
</dd>

### -field <b>ConfigDecoderSpecific</b>

<dd>
<p>[in] A USHORT value that specifies decoder-specific features to configure. For information about a decoder's features, see the specification for that decoder. For a list of decoders, see <a href="https://msdn.microsoft.com/bffcc0da-7b1a-4f70-98f5-4841c8df9f12">Providing Capabilities for Video Decoding</a>. </p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the Windows operating systems.</p>
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
<a href="..\d3dumddi\ns-d3dumddi--d3dddiarg-getcaps.md">D3DDDIARG_GETCAPS</a>
</dt>
<dt>
<a href="..\d3dumddi\ne-d3dumddi--d3dddicaps-type.md">D3DDDICAPS_TYPE</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-getcaps.md">GetCaps</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVADDI_CONFIGPICTUREDECODE structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

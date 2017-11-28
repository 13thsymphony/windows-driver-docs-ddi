---
UID: NC.d3d10umddi.PFND3D10DDI_RESOURCECOPYREGION
title: PFND3D10DDI_RESOURCECOPYREGION
author: windows-driver-content
description: The ResourceCopyRegion function copies a source subresource region to a location on a destination subresource.
old-location: display\resourcecopyregion.htm
old-project: display
ms.assetid: e782dc8c-e34e-4f96-b6d9-c34d7843ed05
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: SETRESULT_INFO, SETRESULT_INFO, *PSETRESULT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ResourceCopyRegion
req.alt-loc: d3d10umddi.h
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

# PFND3D10DDI_RESOURCECOPYREGION callback



## -description
<p>The <i>ResourceCopyRegion</i> function copies a source subresource region to a location on a destination subresource.</p>


## -prototype

````
PFND3D10DDI_RESOURCECOPYREGION ResourceCopyRegion;

VOID APIENTRY ResourceCopyRegion(
  _In_           D3D10DDI_HDEVICE   hDevice,
  _In_           D3D10DDI_HRESOURCE hDstResource,
  _In_           UINT               DstSubresource,
  _In_           UINT               DstX,
  _In_           UINT               DstY,
  _In_           UINT               DstZ,
  _In_           D3D10DDI_HRESOURCE hSrcResource,
  _In_           UINT               SrcSubresource,
  _In_opt_ const D3D10_DDI_BOX      *pSrcBox
)
{ ... }
````


## -parameters
<dl>

### -param <i>hDevice</i> [in]

<dd>
<p> A handle to the display device (graphics context).</p>
</dd>

### -param <i>hDstResource</i> [in]

<dd>
<p> A handle to the destination resource to copy to.</p>
</dd>

### -param <i>DstSubresource</i> [in]

<dd>
<p> An index that indicates the destination subresource to copy to. </p>
</dd>

### -param <i>DstX</i> [in]

<dd>
<p> The x-coordinate of the destination subresource. </p>
</dd>

### -param <i>DstY</i> [in]

<dd>
<p> The y-coordinate of the destination subresource. For one-dimensional (1-D) subresources, <i>DstY</i> is set to zero.</p>
</dd>

### -param <i>DstZ</i> [in]

<dd>
<p> The z-coordinate of the destination subresource. For one-dimensional (1-D) and two-dimensional (2-D) subresources, <i>DstZ</i> is set to zero.</p>
</dd>

### -param <i>hSrcResource</i> [in]

<dd>
<p> A handle to the source resource to copy from.</p>
</dd>

### -param <i>SrcSubresource</i> [in]

<dd>
<p> An index that indicates the source subresource to copy from. </p>
</dd>

### -param <i>pSrcBox</i> [in, optional]

<dd>
<p> A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541925">D3D10_DDI_BOX</a> structure that specifies a box that fits on either the source or destination subresource. If <i>pSrcBox</i> is <b>NULL</b>, the driver should copy the entire source subresouce to the destination.</p>
<p>If the members of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541925">D3D10_DDI_BOX</a> structure are such that <b>left</b>&gt;=<b>right</b>, <b>top</b>&gt;=<b>bottom</b>, or <b>front</b>&gt;=<b>back</b>, then <i>pSrcBox</i> is considered empty, and <i>ResourceCopyRegion</i> must not perform any copy operation.</p>
</dd>
</dl>

## -returns
<p>None</p>

<p>The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-seterror-cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the Remarks section. </p>

## -remarks
<p>The Microsoft Direct3D runtime calls the user-mode display driver's <i>ResourceCopyRegion</i> function to inform the driver to copy from the specified source subresource region to a location on the specified destination subresource. The source and destination subresources cannot be the same subresource of the same resource. Both source and destination resources must be the same type of resource and must have format types (DXGI_FORMAT-typed values) that are convertible to each other. </p>

<p>For buffers, all the coordinates must be in bytes; whereas for textures, all the coordinates must be in pixels. The box that the <i>pSrcBox</i> parameter points to must not extend over the edges of the source subresource region or the destination subresource. The source and the destination resource must not be currently mapped. In addition, the resource creation flags restrict whether the resource can participate in the copy operation. </p>

<p>The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-seterror-cb.md">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <i>ResourceCopyRegion</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.</p>

<p>The driver can implement a <i>ResourceCopyRegion</i> function that can contain a <b>switch</b> statement to process copying and conversion. That is, the driver can implement one <i>ResourceCopyRegion</i> and can set the <b>pfnResourceConvertRegion</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541873">D3D10_1DDI_DEVICEFUNCS</a> structure to point to <i>ResourceCopyRegion</i> along with the <b>pfnResourceCopyRegion</b> member of D3D10_1DDI_DEVICEFUNCS. However, to improve performance, the driver can implement separate <i>ResourceCopyRegion</i> and <i>ResourceConvertRegion</i> functions.</p>

<p>The Direct3D 10.1 version  of <i>ResourceCopyRegion</i> has a major functionality difference from the Direct3D 10.0 version in regard to the <b>ResourceDimension</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff541697">D3D10DDIARG_CREATERESOURCE</a> for the source and destination resources that were created in calls to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-createresource.md">CreateResource(D3D10)</a> function. For the Direct3D 10.0 version  of <i>ResourceCopyRegion</i>, the <b>ResourceDimension</b> member of D3D10DDIARG_CREATERESOURCE for the source and destination resources must match. The Direct3D 10.1 version of <i>ResourceCopyRegion</i> allows a slight relaxation for the <b>ResourceDimension</b> member of D3D10DDIARG_CREATERESOURCE for the source and destination resources. The Direct3D 10.1 version of <i>ResourceCopyRegion</i> allows for the copying of Tex2D source resources on TexCube destination resources or TexCube source resources on Tex2D destination resources. In addition, the distinction between TexCube at the resource level is gone in Direct3D version 10.1. The Direct3D 10.1 version of <i>ResourceCopyRegion</i> only represents whether it can copy a TexCube. In Direct3D version 10.0, copying a resource, validation of a multiple render target, and so on (that is, various operations that required the resource type to be identical) all included the distinction of TexCube to factor into the resource type. In Direct3D version 10.1, the runtime can determine only Tex2D.</p>

<p>The following sections list conditions for copying and converting:</p>

<p><b>Copying</b></p>

<p>For copying, <i>ResourceCopyRegion</i> ensures that the source and destination resources were created through the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-createresource.md">CreateResource(D3D10)</a> function with the following conditions: </p>

<p>The destination resource was not created with the D3D10_DDI_USAGE_IMMUTABLE value set in the <b>Usage</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541697">D3D10DDIARG_CREATERESOURCE</a> structure. </p>

<p>If either the source or destination resource has the D3D10_DDI_BIND_DEPTH_STENCIL bit set in the <b>BindFlags</b> member of the D3D10DDIARG_CREATERESOURCE or is a multi-sampled resource, <i>ResourceCopyRegion</i> verifies that the <i>pSrcBox</i> parameter is <b>NULL</b>, while the <i>DstX</i>, <i>DstY</i>, and <i>DstZ</i> parameters are 0.</p>

<p>The subresource indices are in range.</p>

<p>Alignment restrictions apply to coordinates.</p>

<p>The source and destination resources are not part of the exact same subresource. </p>

<p>Each source and destination resource format that is specified in the <b>Format</b> member of D3D10DDIARG_CREATERESOURCE is in the same typeless group. </p>

<p>The source and destination resources must have the same number of samples and quality levels; except for single-sampled resources, which must only have the same number of samples. </p>

<p><i>ResourceCopyRegion</i> does not ensure that the source box that is offset by the destination offsets fits entirely on the resource. <i>ResourceCopyRegion</i> also does not ensure that no subresources are currently mapped. </p>

<p><b>Converting</b></p>

<p>For conversion, <i>ResourceCopyRegion</i> ensures that the source and destination resources were created through the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-createresource.md">CreateResource(D3D10)</a> function with the following conditions:</p>

<p>The destination resource was not created with the D3D10_DDI_USAGE_IMMUTABLE value set in the <b>Usage</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541697">D3D10DDIARG_CREATERESOURCE</a> structure. </p>

<p>If either the source or destination resource has the D3D10_DDI_BIND_DEPTH_STENCIL bit set in the <b>BindFlags</b> member of the D3D10DDIARG_CREATERESOURCE or is a multi-sampled resource, <i>ResourceCopyRegion</i> verifies that the <i>pSrcBox</i> parameter is <b>NULL</b>, while the <i>DstX</i>, <i>DstY</i>, and <i>DstZ</i> parameters are 0.</p>

<p>The subresource indices are in range.</p>

<p>Alignment restrictions apply to coordinates.</p>

<p>The source and destination resources are not part of the exact same subresource. </p>

<p>Each source and destination resource format that is specified in the <b>Format</b> member of D3D10DDIARG_CREATERESOURCE is in the same typeless group. </p>

<p>Each source and destination resource format that is specified in the <b>Format</b> member of D3D10DDIARG_CREATERESOURCE supports the appropriate conversion operation. </p>

<p>The source and destination resources must have the same number of samples and quality levels; except for single-sampled resources, which must only have the same number of samples. </p>

<p><i>ResourceCopyRegion</i> does not ensure that no subresources are currently mapped. <i>ResourceCopyRegion</i> also does not ensure that the source box that is offset by the destination offsets fits entirely on the resource.</p>

<p>The Microsoft Direct3D runtime calls the user-mode display driver's <i>ResourceCopyRegion</i> function to inform the driver to copy from the specified source subresource region to a location on the specified destination subresource. The source and destination subresources cannot be the same subresource of the same resource. Both source and destination resources must be the same type of resource and must have format types (DXGI_FORMAT-typed values) that are convertible to each other. </p>

<p>For buffers, all the coordinates must be in bytes; whereas for textures, all the coordinates must be in pixels. The box that the <i>pSrcBox</i> parameter points to must not extend over the edges of the source subresource region or the destination subresource. The source and the destination resource must not be currently mapped. In addition, the resource creation flags restrict whether the resource can participate in the copy operation. </p>

<p>The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-seterror-cb.md">pfnSetErrorCb</a> function, the Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <i>ResourceCopyRegion</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.</p>

<p>The driver can implement a <i>ResourceCopyRegion</i> function that can contain a <b>switch</b> statement to process copying and conversion. That is, the driver can implement one <i>ResourceCopyRegion</i> and can set the <b>pfnResourceConvertRegion</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541873">D3D10_1DDI_DEVICEFUNCS</a> structure to point to <i>ResourceCopyRegion</i> along with the <b>pfnResourceCopyRegion</b> member of D3D10_1DDI_DEVICEFUNCS. However, to improve performance, the driver can implement separate <i>ResourceCopyRegion</i> and <i>ResourceConvertRegion</i> functions.</p>

<p>The Direct3D 10.1 version  of <i>ResourceCopyRegion</i> has a major functionality difference from the Direct3D 10.0 version in regard to the <b>ResourceDimension</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff541697">D3D10DDIARG_CREATERESOURCE</a> for the source and destination resources that were created in calls to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-createresource.md">CreateResource(D3D10)</a> function. For the Direct3D 10.0 version  of <i>ResourceCopyRegion</i>, the <b>ResourceDimension</b> member of D3D10DDIARG_CREATERESOURCE for the source and destination resources must match. The Direct3D 10.1 version of <i>ResourceCopyRegion</i> allows a slight relaxation for the <b>ResourceDimension</b> member of D3D10DDIARG_CREATERESOURCE for the source and destination resources. The Direct3D 10.1 version of <i>ResourceCopyRegion</i> allows for the copying of Tex2D source resources on TexCube destination resources or TexCube source resources on Tex2D destination resources. In addition, the distinction between TexCube at the resource level is gone in Direct3D version 10.1. The Direct3D 10.1 version of <i>ResourceCopyRegion</i> only represents whether it can copy a TexCube. In Direct3D version 10.0, copying a resource, validation of a multiple render target, and so on (that is, various operations that required the resource type to be identical) all included the distinction of TexCube to factor into the resource type. In Direct3D version 10.1, the runtime can determine only Tex2D.</p>

<p>The following sections list conditions for copying and converting:</p>

<p><b>Copying</b></p>

<p>For copying, <i>ResourceCopyRegion</i> ensures that the source and destination resources were created through the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-createresource.md">CreateResource(D3D10)</a> function with the following conditions: </p>

<p>The destination resource was not created with the D3D10_DDI_USAGE_IMMUTABLE value set in the <b>Usage</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541697">D3D10DDIARG_CREATERESOURCE</a> structure. </p>

<p>If either the source or destination resource has the D3D10_DDI_BIND_DEPTH_STENCIL bit set in the <b>BindFlags</b> member of the D3D10DDIARG_CREATERESOURCE or is a multi-sampled resource, <i>ResourceCopyRegion</i> verifies that the <i>pSrcBox</i> parameter is <b>NULL</b>, while the <i>DstX</i>, <i>DstY</i>, and <i>DstZ</i> parameters are 0.</p>

<p>The subresource indices are in range.</p>

<p>Alignment restrictions apply to coordinates.</p>

<p>The source and destination resources are not part of the exact same subresource. </p>

<p>Each source and destination resource format that is specified in the <b>Format</b> member of D3D10DDIARG_CREATERESOURCE is in the same typeless group. </p>

<p>The source and destination resources must have the same number of samples and quality levels; except for single-sampled resources, which must only have the same number of samples. </p>

<p><i>ResourceCopyRegion</i> does not ensure that the source box that is offset by the destination offsets fits entirely on the resource. <i>ResourceCopyRegion</i> also does not ensure that no subresources are currently mapped. </p>

<p><b>Converting</b></p>

<p>For conversion, <i>ResourceCopyRegion</i> ensures that the source and destination resources were created through the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-createresource.md">CreateResource(D3D10)</a> function with the following conditions:</p>

<p>The destination resource was not created with the D3D10_DDI_USAGE_IMMUTABLE value set in the <b>Usage</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541697">D3D10DDIARG_CREATERESOURCE</a> structure. </p>

<p>If either the source or destination resource has the D3D10_DDI_BIND_DEPTH_STENCIL bit set in the <b>BindFlags</b> member of the D3D10DDIARG_CREATERESOURCE or is a multi-sampled resource, <i>ResourceCopyRegion</i> verifies that the <i>pSrcBox</i> parameter is <b>NULL</b>, while the <i>DstX</i>, <i>DstY</i>, and <i>DstZ</i> parameters are 0.</p>

<p>The subresource indices are in range.</p>

<p>Alignment restrictions apply to coordinates.</p>

<p>The source and destination resources are not part of the exact same subresource. </p>

<p>Each source and destination resource format that is specified in the <b>Format</b> member of D3D10DDIARG_CREATERESOURCE is in the same typeless group. </p>

<p>Each source and destination resource format that is specified in the <b>Format</b> member of D3D10DDIARG_CREATERESOURCE supports the appropriate conversion operation. </p>

<p>The source and destination resources must have the same number of samples and quality levels; except for single-sampled resources, which must only have the same number of samples. </p>

<p><i>ResourceCopyRegion</i> does not ensure that no subresources are currently mapped. <i>ResourceCopyRegion</i> also does not ensure that the source box that is offset by the destination offsets fits entirely on the resource.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
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
<dt>D3d10umddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541925">D3D10_DDI_BOX</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-seterror-cb.md">pfnSetErrorCb</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_RESOURCECOPYREGION callback function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

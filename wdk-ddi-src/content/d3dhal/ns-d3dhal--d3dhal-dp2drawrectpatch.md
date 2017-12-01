---
UID: NS.d3dhal._D3DHAL_DP2DRAWRECTPATCH
title: D3DHAL_DP2DRAWRECTPATCH
author: windows-driver-content
description: DirectX 8.0 and later versions only.
old-location: display\d3dhal_dp2drawrectpatch.htm
old-project: display
ms.assetid: 892fe11a-4dfd-43cb-8f9a-b148d81a087f
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DHAL_DP2DRAWRECTPATCH, D3DHAL_DP2DRAWRECTPATCH
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DHAL_DP2DRAWRECTPATCH
req.alt-loc: d3dhal.h
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

# D3DHAL_DP2DRAWRECTPATCH structure



## -description
<p>
   DirectX 8.0 and later versions only.
   </p>
<p>D3DHAL_DRAWRECTPATCH is parsed from the command buffer by the <a href="..\d3dhal\nc-d3dhal-lpd3dhal-drawprimitives2cb.md">D3dDrawPrimitives2</a> callback when the <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2command.md">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_DRAWRECTPATCH, and is used to render a rectangular patch.</p>


## -syntax

````
typedef struct _D3DHAL_DP2DRAWRECTPATCH {
  DWORD Handle;
  DWORD Flags;
} D3DHAL_DP2DRAWRECTPATCH, *LPD3DHAL_DP2DRAWRECTPATCH;
````


## -struct-fields
<dl>

### -field <b>Handle</b>

<dd>
<p>Specifies the handle associated with the surface.</p>
</dd>

### -field <b>Flags</b>

<dd>
<p>Specifies what, if any, additional information follows the D3DHAL_DP2DRAWRECTPATCH data structure in the DP2 stream.</p>
</dd>
</dl>

## -remarks
<p>The <b>Handle</b> member is used to associate the surface with a handle, so that the next time this surface is drawn, there is no need to respecify the D3DRECTPATCH_INFO data structure for this patch. This makes it possible for the driver to precompute and cache forward difference coefficients and/or any other information, which in turn allows subsequent D3DDP2OP_DRAWRECTPATCH tokens using the same handle to execute more efficiently. D3DRECTPATCH_INFO is described in the latest DirectX SDK documentation. </p>

<p>The actual value of <b>Handle</b> is determined by the application and is not under runtime control. Therefore, the driver should be prepared to cope with any value that can be specified by a DWORD. The special handle value of zero means that the patch is dynamic and there is no point precomputing or caching information for this patch. A subzero value for <b>Handle</b> means the patch is static (or updated with low frequency) and precomputation and caching are possible.</p>

<p>The <b>Flags</b> member is used to communicate what, if any, additional information follows the D3DHAL_DP2DRAWRECTPATCH data structure in the DP2 stream. If RTPATCHFLAG_HASSEGS is specified then four floating-point values follow D3DHAL_DP2DRAWRECTPATCH in the DP2 stream. These floats give the segment counts for each of the four edges of the rectangular patch and override the value of the render state D3DRS_PATCHSEGMENTS. If RTPATCHFLAG_HASINFO is specified then a D3DRECTPATCH_INFO data structure follows in the DP2 stream. If both flags are specified the four floats specifying segment counts follow D3DHAL_DP2DRAWRECTPATCH and the D3DRECTPATCH_INFO structure follows the floating-point values.</p>

<p>There are four scenarios a driver must handle when processing D3DDP2OP_DRAWRECTPATCH.</p>

<p>If <b>Handle</b> is zero, then the patch is dynamic and no precomputation or caching should be performed. In this case, a D3DRECTPATCH_INFO follows D3DHAL_DP2DRAWRECTPATCH in the DP2 stream (and the flag RTPATCHFLAG_HASINFO is set to indicate the presence of the D3DRECTPATCH_INFO data structure). Optionally, RTPATCHFLAG_HASSEGS may also be set to indicate the presence of the segment information. However, if this is omitted, the value of the render state D3DRS_PATCHSEGMENTS should be used instead.</p>

<p>If <b>Handle</b> is subzero and the handle value has not been specified by an earlier D3DDP2OP_DRAWRECTPATCH, this indicates that a new cacheable patch is being drawn. The driver should allocate memory to store cached data and add this data to its patch handle table. Because this patch has not been seen before, the RTPATCHFLAG_HASINFO flag should be set and a D3DRECTPATCH_INFO structure should follow in the DP2 stream. The runtime does not guarantee this, however, and the driver should verify the presence of the patch information by testing the flag. If no information is specified, this token should be ignored and no handle should be allocated in the driver's patch handle table. Optionally, RTPATCHFLAG_HASSEGS may also be set to indicate the presence of the segment information. However, if this is omitted, the value of the render state D3DRS_PATCHSEGMENTS should be used instead. </p>

<p>If <b>Handle</b> is subzero, the handle value has been specified by an earlier D3DDP2OP_DRAWRECTPATCH token, and the <b>Flags</b> field contains RTPATCHFLAG_HASINFO, then the definition for the patch is being updated. A D3DRECTPATCH_INFO data structure follows in the DP2 stream and the driver should use that to recompute and recache patch information. Optionally, RTPATCHFLAG_HASSEGS may also be set to indicate the presence of the segment information. However, if this is omitted, the value of the render state D3DRS_PATCHSEGMENTS should be used instead.</p>

<p>If <b>Handle</b> is subzero, the handle value has been specified by an earlier D3DDP2OP_DRAWRECTPATCH token, and the <b>Flags</b> field does not contain RTPATCHFLAG_HASINFO, then the cached information should be used for drawing the patch. In this case, the current vertex streams are ignored; the cached information should be used instead. However, it is still possible in this case for a new segment information to be specified. Therefore, the driver should check for the flag RTPATCHFLAG_HASSEGS and handle specified segment information even if using a cached patch.</p>

<p>The driver receives notification that cached patch information is be released via the render state D3DRS_DELETERTPATCH. The value of this render state is the patch to be deleted.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dhal.h (include D3dhal.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>D3DDP2OP_DRAWRECTPATCH</dt>
<dt>
<a href="..\d3dhal\nc-d3dhal-lpd3dhal-drawprimitives2cb.md">D3dDrawPrimitives2</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal--d3dhal-dp2command.md">D3DHAL_DP2COMMAND</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal--d3dhal-dp2drawtripatch.md">D3DHAL_DP2DRAWTRIPATCH</a>
</dt>
<dt>D3DRS_DELETERTPATCH</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2DRAWRECTPATCH structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>

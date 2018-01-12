---
UID: NC:d3dumddi.PFND3DDDI_DRAWRECTPATCH
title: PFND3DDDI_DRAWRECTPATCH
author: windows-driver-content
description: The DrawRectPatch function draws a new or cached rectangular patch or updates the specification of a previously defined patch.
old-location: display\drawrectpatch.htm
old-project: display
ms.assetid: c0e3046c-f2af-4406-ac5a-c3e44f40b1fd
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_PTE, DXGK_PTE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DrawRectPatch
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
req.typenames: DXGK_PTE
---

# PFND3DDDI_DRAWRECTPATCH callback



## -description
The <b>DrawRectPatch</b> function draws a new or cached rectangular patch or updates the specification of a previously defined patch.



## -prototype

````
PFND3DDDI_DRAWRECTPATCH DrawRectPatch;

__checkReturn HRESULT APIENTRY DrawRectPatch(
  _In_       HANDLE                  hDevice,
  _In_ const D3DDDIARG_DRAWRECTPATCH *pData,
  _In_ const D3DDDIRECTPATCH_INFO    *pInfo,
  _In_ const FLOAT                   *pPatch
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).


### -param pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_drawrectpatch.md">D3DDDIARG_DRAWRECTPATCH</a> structure that describes the rectangular patch to draw.


### -param pInfo [in]

 Optional. A pointer to a D3DDDIRECTPATCH_INFO structure that describes information about the rectangular patch.


### -param pPatch [in]

 Optional. A pointer to a buffer that contains four floating-point values (D3DFLOAT[4]) that provide the segment counts for each of the four edges of the rectangular patch.


## -returns
<b>DrawRectPatch</b> returns S_OK or an appropriate error result if the rectangular patch is not successfully drawn.


## -remarks
When the Microsoft Direct3D runtime calls<i>pPatch</i> the user-mode display driver's <b>DrawRectPatch</b> function, it can optionally supply information in the <i>pInfo</i> and  parameters. The runtime sets flags in the <b>Flags</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_drawrectpatch.md">D3DDDIARG_DRAWRECTPATCH</a> structure that is specified by <i>pData</i> to indicate if it supplies this optional information. 

The runtime supplies a UINT value in the <b>Handle</b> member of D3DDDIARG_DRAWRECTPATCH to refer to the patch surface. Whenever the runtime redraws the patch surface, it passes the patch handle value and is not required to re-specify the D3DDDIRECTPATCH_INFO data structure for the patch surface. The user-mode display driver can precompute and cache forward-difference coefficients and any other information. Therefore, subsequent calls to the driver's <b>DrawRectPatch</b> function that use the same patch handle value run more efficiently.

The actual value in <b>Handle</b> is determined by the application and is not under runtime control. Therefore, the driver must handle any value that can be specified by a UINT. 

The special <b>Handle</b> value of zero indicates that the patch is dynamic; therefore, the driver cannot precompute or cache information for the patch. A nonzero value for <b>Handle</b> indicates that the patch is static (or updated with low frequency); therefore, the driver can precompute and cache information for the patch.

The driver must handle the following scenarios in its <b>DrawRectPatch</b> function: 

If the <b>Handle</b> member is zero, the patch is dynamic. The driver should neither precompute nor cache information for the patch. In this situation, the runtime passes a pointer to a D3DDDIRECTPATCH_INFO structure in the <i>pInfo</i> parameter and sets the RTPATCHFLAG_HASINFO flag in the <b>Flags</b> member of the D3DDDIARG_DRAWRECTPATCH structure to indicate the presence of the D3DDDIRECTPATCH_INFO structure at <i>pInfo</i>. Optionally, the runtime can also set the RTPATCHFLAG_HASSEGS flag in <b>Flags</b> to indicate the presence of the segment information that is specified by the <i>pPatch</i> parameter. However, if the runtime does not supply segment information at <i>pPatch</i>, the runtime should instead use the D3DRS_PATCHSEGMENTS render state value.

If a nonzero <b>Handle</b> value has not been previously specified in an earlier call to the driver's <b>DrawRectPatch</b> function, the runtime draws a new cacheable patch. The driver should allocate memory to store cached data and should add this data to its patch handle table. Because the runtime has not previously drawn this patch, the runtime should set the RTPATCHFLAG_HASINFO flag and pass a pointer to a D3DDDIRECTPATCH_INFO structure in the <i>pInfo</i> parameter. The driver must check for the RTPATCHFLAG_HASINFO flag to verify the presence of the patch information. If no patch information is specified, the driver should ignore the <b>DrawRectPatch</b> call and should not allocate memory for cached data in its patch handle table. Optionally, the runtime can set the RTPATCHFLAG_HASSEGS flag to indicate the presence of the segment information. However, if the runtime does not supply segment information at <i>pPatch</i>, the runtime should instead use the D3DRS_PATCHSEGMENTS render state value.

If a nonzero <b>Handle</b> value has been previously specified in an earlier call to the driver's <b>DrawRectPatch</b> function and the RTPATCHFLAG_HASINFO flag is set, the runtime updates the definition for the patch. The runtime passes a pointer to a D3DDDIRECTPATCH_INFO structure in the <i>pInfo</i> parameter, and the driver must recompute and recache the patch information. Optionally, the runtime can set the RTPATCHFLAG_HASSEGS flag to indicate the presence of the segment information. However, if the runtime does not supply segment information at <i>pPatch</i>, the runtime should instead use the D3DRS_PATCHSEGMENTS render state value.

If a nonzero <b>Handle</b> value has been previously specified in an earlier call to the driver's <b>DrawRectPatch</b> function and the RTPATCHFLAG_HASINFO flag is not set, the runtime redraws the patch. The driver should use the cached information to draw the patch. In this situation, the driver ignores the current vertex streams, and the cached information is used instead. However, the runtime can still specify new segment information; therefore, the driver should check for the RTPATCHFLAG_HASSEGS flag and handle specified segment information even if it uses a cached patch.

The driver receives notification to release cached patch information through the D3DRS_DELETERTPATCH render state. The value of this render state is the patch to delete.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.

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
<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_drawrectpatch.md">D3DDDIARG_DRAWRECTPATCH</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_DRAWRECTPATCH callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


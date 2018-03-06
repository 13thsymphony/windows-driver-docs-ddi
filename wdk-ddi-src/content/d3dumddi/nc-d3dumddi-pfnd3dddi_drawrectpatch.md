---
UID: NC:d3dumddi.PFND3DDDI_DRAWRECTPATCH
title: PFND3DDDI_DRAWRECTPATCH
author: windows-driver-content
description: The DrawRectPatch function draws a new or cached rectangular patch or updates the specification of a previously defined patch.
old-location: display\drawrectpatch.htm
old-project: display
ms.assetid: c0e3046c-f2af-4406-ac5a-c3e44f40b1fd
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DrawRectPatch, DrawRectPatch callback function [Display Devices], PFND3DDDI_DRAWRECTPATCH, UserModeDisplayDriver_Functions_a32bf010-d5a9-4cf7-b885-4f0fb407a4ad.xml, d3dumddi/DrawRectPatch, display.drawrectpatch
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	DrawRectPatch
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_DRAWRECTPATCH callback function
The <b>DrawRectPatch</b> function draws a new or cached rectangular patch or updates the specification of a previously defined patch.

## Syntax

```
PFND3DDDI_DRAWRECTPATCH Pfnd3dddiDrawrectpatch;

HRESULT Pfnd3dddiDrawrectpatch(
  HANDLE hDevice,
  CONST D3DDDIARG_DRAWRECTPATCH *,
  CONST D3DDDIRECTPATCH_INFO *,
  CONST FLOAT *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`



`*`



`*`




## Return Value

<b>DrawRectPatch</b> returns S_OK or an appropriate error result if the rectangular patch is not successfully drawn.

## Remarks

When the Microsoft Direct3D runtime calls<i>pPatch</i> the user-mode display driver's <b>DrawRectPatch</b> function, it can optionally supply information in the <i>pInfo</i> and  parameters. The runtime sets flags in the <b>Flags</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_drawrectpatch.md">D3DDDIARG_DRAWRECTPATCH</a> structure that is specified by <i>pData</i> to indicate if it supplies this optional information. 

The runtime supplies a UINT value in the <b>Handle</b> member of D3DDDIARG_DRAWRECTPATCH to refer to the patch surface. Whenever the runtime redraws the patch surface, it passes the patch handle value and is not required to re-specify the D3DDDIRECTPATCH_INFO data structure for the patch surface. The user-mode display driver can precompute and cache forward-difference coefficients and any other information. Therefore, subsequent calls to the driver's <b>DrawRectPatch</b> function that use the same patch handle value run more efficiently.

The actual value in <b>Handle</b> is determined by the application and is not under runtime control. Therefore, the driver must handle any value that can be specified by a UINT. 

The special <b>Handle</b> value of zero indicates that the patch is dynamic; therefore, the driver cannot precompute or cache information for the patch. A nonzero value for <b>Handle</b> indicates that the patch is static (or updated with low frequency); therefore, the driver can precompute and cache information for the patch.

The driver must handle the following scenarios in its <b>DrawRectPatch</b> function: 

<ul>
<li>
If the <b>Handle</b> member is zero, the patch is dynamic. The driver should neither precompute nor cache information for the patch. In this situation, the runtime passes a pointer to a D3DDDIRECTPATCH_INFO structure in the <i>pInfo</i> parameter and sets the RTPATCHFLAG_HASINFO flag in the <b>Flags</b> member of the D3DDDIARG_DRAWRECTPATCH structure to indicate the presence of the D3DDDIRECTPATCH_INFO structure at <i>pInfo</i>. Optionally, the runtime can also set the RTPATCHFLAG_HASSEGS flag in <b>Flags</b> to indicate the presence of the segment information that is specified by the <i>pPatch</i> parameter. However, if the runtime does not supply segment information at <i>pPatch</i>, the runtime should instead use the D3DRS_PATCHSEGMENTS render state value.

</li>
<li>
If a nonzero <b>Handle</b> value has not been previously specified in an earlier call to the driver's <b>DrawRectPatch</b> function, the runtime draws a new cacheable patch. The driver should allocate memory to store cached data and should add this data to its patch handle table. Because the runtime has not previously drawn this patch, the runtime should set the RTPATCHFLAG_HASINFO flag and pass a pointer to a D3DDDIRECTPATCH_INFO structure in the <i>pInfo</i> parameter. The driver must check for the RTPATCHFLAG_HASINFO flag to verify the presence of the patch information. If no patch information is specified, the driver should ignore the <b>DrawRectPatch</b> call and should not allocate memory for cached data in its patch handle table. Optionally, the runtime can set the RTPATCHFLAG_HASSEGS flag to indicate the presence of the segment information. However, if the runtime does not supply segment information at <i>pPatch</i>, the runtime should instead use the D3DRS_PATCHSEGMENTS render state value.

</li>
<li>
If a nonzero <b>Handle</b> value has been previously specified in an earlier call to the driver's <b>DrawRectPatch</b> function and the RTPATCHFLAG_HASINFO flag is set, the runtime updates the definition for the patch. The runtime passes a pointer to a D3DDDIRECTPATCH_INFO structure in the <i>pInfo</i> parameter, and the driver must recompute and recache the patch information. Optionally, the runtime can set the RTPATCHFLAG_HASSEGS flag to indicate the presence of the segment information. However, if the runtime does not supply segment information at <i>pPatch</i>, the runtime should instead use the D3DRS_PATCHSEGMENTS render state value.

</li>
<li>
If a nonzero <b>Handle</b> value has been previously specified in an earlier call to the driver's <b>DrawRectPatch</b> function and the RTPATCHFLAG_HASINFO flag is not set, the runtime redraws the patch. The driver should use the cached information to draw the patch. In this situation, the driver ignores the current vertex streams, and the cached information is used instead. However, the runtime can still specify new segment information; therefore, the driver should check for the RTPATCHFLAG_HASSEGS flag and handle specified segment information even if it uses a cached patch.

</li>
</ul>
The driver receives notification to release cached patch information through the D3DRS_DELETERTPATCH render state. The value of this render state is the patch to delete.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_drawrectpatch.md">D3DDDIARG_DRAWRECTPATCH</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_DRAWRECTPATCH callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTARGETMODESET_GETNUMMODES
title: DXGKDDI_VIDPNTARGETMODESET_GETNUMMODES
author: windows-driver-content
description: The pfnGetNumModes function returns the number of target modes in a specified VidPN target mode set.
old-location: display\dxgk_vidpntargetmodeset_interface_pfngetnummodes.htm
old-project: display
ms.assetid: 1197989a-c76e-4dee-a1c7-677b6558677c
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.dxgk_vidpntargetmodeset_interface_pfngetnummodes, pfnGetNumModes callback function [Display Devices], pfnGetNumModes, DXGKDDI_VIDPNTARGETMODESET_GETNUMMODES, DXGKDDI_VIDPNTARGETMODESET_GETNUMMODES, d3dkmddi/pfnGetNumModes, VidPnFunctions_f2fa9ea6-6ce7-485d-bcd2-b3c340ca66fc.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dkmddi.h
apiname:
-	pfnGetNumModes
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKDDI_VIDPNTARGETMODESET_GETNUMMODES callback function
The <b>pfnGetNumModes</b> function returns the number of target modes in a specified VidPN target mode set.

## Syntax

```
DXGKDDI_VIDPNTARGETMODESET_GETNUMMODES DxgkddiVidpntargetmodesetGetnummodes;

NTSTATUS DxgkddiVidpntargetmodesetGetnummodes(
  IN_CONST_D3DKMDT_HVIDPNTARGETMODESET hVidPnTargetModeSet,
  OUT_PSIZE_T_CONST pNumTargetModes
)
{...}
```

## Parameters

`hVidPnTargetModeSet`

A handle to a VidPN target mode set object. The display miniport driver previously obtained this handle by calling the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpn_acquiretargetmodeset.md">pfnAcquireTargetModeSet</a> function of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_vidpn_interface.md">DXGK_VIDPN_INTERFACE</a> interface.

`pNumTargetModes`

A pointer to a SIZE_T-typed variable that receives the number of target modes in the set.


## Return Value

The <b>pfnGetNumModes</b> function returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The function succeeded. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDPN_TARGETMODESET</b></dt>
</dl>
</td>
<td width="60%">
The handle supplied in <i>hVidPnTargetModeSet</i> was invalid.

</td>
</tr>
</table>

## Remarks

The D3DKMDT_HVIDPNTARGETMODESET data type is defined in <i>D3dkmdt.h</i>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntargetmodeset_acquirefirstmodeinfo.md">pfnAcquireFirstModeInfo</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_vidpntargetmodeset_acquirenextmodeinfo.md">pfnAcquireNextModeInfo</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_VIDPNTARGETMODESET_GETNUMMODES callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
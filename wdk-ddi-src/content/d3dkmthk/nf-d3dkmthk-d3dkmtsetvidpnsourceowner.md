---
UID : NF:d3dkmthk.D3DKMTSetVidPnSourceOwner
title : D3DKMTSetVidPnSourceOwner function
author : windows-driver-content
description : The D3DKMTSetVidPnSourceOwner function sets and releases the video present source in the path of a video present network (VidPN) topology that owns the VidPN.
old-location : display\d3dkmtsetvidpnsourceowner.htm
old-project : display
ms.assetid : e75020cf-39b4-434c-b071-dc75de6cc81b
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3DKMTSetVidPnSourceOwner, d3dkmthk/D3DKMTSetVidPnSourceOwner, display.d3dkmtsetvidpnsourceowner, D3DKMTSetVidPnSourceOwner function [Display Devices], OpenGL_Functions_3c0b89d9-b3d6-4668-a227-3bc7d0ed2f2f.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : d3dkmthk.h
req.include-header : D3dkmthk.h
req.target-type : Universal
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Gdi32.lib
req.dll : Gdi32.dll
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : D3DKMT_DRIVERVERSION
---


# D3DKMTSetVidPnSourceOwner function
The <b>D3DKMTSetVidPnSourceOwner</b> function sets and releases the video present source in the path of a video present network (VidPN) topology that owns the VidPN.

## Syntax

````
NTSTATUS APIENTRY D3DKMTSetVidPnSourceOwner(
  _In_ const D3DKMT_SETVIDPNSOURCEOWNER *pData
);
````

## Parameters

`D3DKMT_SETVIDPNSOURCEOWNER`

TBD


## Return Value

<b>D3DKMTSetVidPnSourceOwner</b> returns one of the following values:
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
The video present source was successfully set or released.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>
</td>
<td width="60%">
The graphics adapter was stopped or the display device was reset.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_VIDPN_SOURCE_IN_USE</b></dt>
</dl>
</td>
<td width="60%">
The video present source that is specified by an element in the array that the  <b>pVidPnSourceId</b> member of <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_setvidpnsourceowner.md">D3DKMT_SETVIDPNSOURCEOWNER</a> specifies is already owned by a display mode manager (DMM) client and cannot be used until the client releases the video present source.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDEO_PRESENT_SOURCE</b></dt>
</dl>
</td>
<td width="60%">
The video present source that is specified by an element in the array that the  <b>pVidPnSourceId</b> member of <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_setvidpnsourceowner.md">D3DKMT_SETVIDPNSOURCEOWNER</a> specifies is invalid. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect.

</td>
</tr>
</table> 

This function might also return other NTSTATUS values.

## Remarks

To set ownership of video present sources, the OpenGL installable client driver (ICD) sets values in the array that the <b>pType</b> member of the <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_setvidpnsourceowner.md">D3DKMT_SETVIDPNSOURCEOWNER</a> structure specifies, identifiers of the video present sources in the array that the <b>pVidPnSourceId</b> member of D3DKMT_SETVIDPNSOURCEOWNER specifies, and the number of video present sources in the <b>VidPnSourceCount</b> member of D3DKMT_SETVIDPNSOURCEOWNER. 

To release ownership of any video present sources, the ICD sets <b>pType</b> and <b>pVidPnSourceId</b> to <b>NULL</b> and <b>VidPnSourceCount</b> to zero in D3DKMT_SETVIDPNSOURCEOWNER.

The ICD passes a pointer to <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_setvidpnsourceowner.md">D3DKMT_SETVIDPNSOURCEOWNER</a> in the <i>pData</i> parameter in a call to <b>D3DKMTSetVidPnSourceOwner</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Target Platform** | Universal |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |
| **Library** | Gdi32.lib |
| **DLL** | Gdi32.dll |

## See Also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_setvidpnsourceowner.md">D3DKMT_SETVIDPNSOURCEOWNER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTSetVidPnSourceOwner function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
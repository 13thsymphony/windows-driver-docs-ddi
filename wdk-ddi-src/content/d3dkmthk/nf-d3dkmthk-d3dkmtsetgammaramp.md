---
UID : NF:d3dkmthk.D3DKMTSetGammaRamp
title : D3DKMTSetGammaRamp function
author : windows-driver-content
description : The D3DKMTSetGammaRamp function sets the gamma ramp.
old-location : display\d3dkmtsetgammaramp.htm
old-project : display
ms.assetid : 48f1d2ba-747a-4588-8238-db6ac2aa89d6
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.d3dkmtsetgammaramp, d3dkmthk/D3DKMTSetGammaRamp, D3DKMTSetGammaRamp, D3DKMTSetGammaRamp function [Display Devices], OpenGL_Functions_4d684cea-8528-489d-bc35-b70a5f05a57b.xml
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


# D3DKMTSetGammaRamp function
The <b>D3DKMTSetGammaRamp</b> function sets the gamma ramp.

## Syntax

````
NTSTATUS APIENTRY D3DKMTSetGammaRamp(
  _In_ const D3DKMT_SETGAMMARAMP *pData
);
````

## Parameters

`D3DKMT_SETGAMMARAMP`

TBD


## Return Value

<b>D3DKMTSetGammaRamp</b> returns one of the following values:
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
The gamma ramp was successfully set.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>
</td>
<td width="60%">
The graphics adapter was stopped.

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


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_setgammaramp.md">D3DKMT_SETGAMMARAMP</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTSetGammaRamp function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
---
UID: NC:d3dkmthk.PFND3DKMT_OUTPUTDUPLRELEASEFRAME
title: PFND3DKMT_OUTPUTDUPLRELEASEFRAME
author: windows-driver-content
description: Indicates that the driver has finished processing the duplicated desktop image.
old-location: display\d3dkmtoutputduplreleaseframe.htm
old-project: display
ms.assetid: 07bbc201-0320-4f26-be0a-27c06763813f
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMTOutputDuplReleaseFrame, D3DKMTOutputDuplReleaseFrame callback function [Display Devices], PFND3DKMT_OUTPUTDUPLRELEASEFRAME, d3dkmthk/D3DKMTOutputDuplReleaseFrame, display.d3dkmtoutputduplreleaseframe
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3dkmthk.h
api_name:
-	D3DKMTOutputDuplReleaseFrame
product: Windows
targetos: Windows
req.typenames: DXGK_TARGETMODE_DETAIL_TIMING
---


# PFND3DKMT_OUTPUTDUPLRELEASEFRAME callback function
Indicates that the driver has finished processing the duplicated desktop image.

## Syntax

```
PFND3DKMT_OUTPUTDUPLRELEASEFRAME Pfnd3dkmtOutputduplreleaseframe;

NTSTATUS Pfnd3dkmtOutputduplreleaseframe(
  D3DKMT_OUTPUTDUPL_RELEASE_FRAME *
)
{...}
```

## Parameters

`*`




## Return Value

Returns one of the following values:

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
The function performed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER </b></dt>
</dl>
</td>
<td width="60%">

         Parameters were validated and determined to be incorrect.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The context of the process could not be found.

</td>
</tr>
</table>
 

This function might also return other NTSTATUS values.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Universal |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406533">D3DKMT_OUTPUTDUPL_RELEASE_FRAME</a>
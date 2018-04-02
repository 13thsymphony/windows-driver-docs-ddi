---
UID: NC:d3dkmthk.PFND3DKMT_CLOSEADAPTER
title: PFND3DKMT_CLOSEADAPTER
author: windows-driver-content
description: The D3DKMTCloseAdapter function closes a graphics adapter that was previously opened by using the D3DKMTOpenAdapterFromHdc function.
old-location: display\d3dkmtcloseadapter.htm
old-project: display
ms.assetid: d8f1a47b-4ba0-41e0-a6e3-0589e1efcf06
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMTCloseAdapter, D3DKMTCloseAdapter callback function [Display Devices], OpenGL_Functions_531edcbd-0ec0-4ae7-8a1a-31ed47084bba.xml, PFND3DKMT_CLOSEADAPTER, d3dkmthk/D3DKMTCloseAdapter, display.d3dkmtcloseadapter
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
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
-	d3dkmthk.h
api_name:
-	D3DKMTCloseAdapter
product: Windows
targetos: Windows
req.typenames: DXGK_TARGETMODE_DETAIL_TIMING
---


# PFND3DKMT_CLOSEADAPTER callback function
The <b>D3DKMTCloseAdapter</b> function closes a graphics adapter that was previously opened by using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547047">D3DKMTOpenAdapterFromHdc</a> function.

## Syntax

```
PFND3DKMT_CLOSEADAPTER Pfnd3dkmtCloseadapter;

NTSTATUS Pfnd3dkmtCloseadapter(
  CONST D3DKMT_CLOSEADAPTER *
)
{...}
```

## Parameters

`*`




## Return Value

<b>D3DKMTCloseAdapter</b> returns one of the following values:

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
The adapter was closed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect or the Windows Vista display driver model was not used.

</td>
</tr>
</table>
 

This function might also return other NTSTATUS values.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Universal |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547789">D3DKMT_CLOSEADAPTER</a>
---
UID: NF:d3dkmthk.D3DKMTSetContextSchedulingPriority
title: D3DKMTSetContextSchedulingPriority function
author: windows-driver-content
description: The D3DKMTSetContextSchedulingPriority function sets the scheduling priority for a device context.
old-location: display\d3dkmtsetcontextschedulingpriority.htm
old-project: display
ms.assetid: 781d5a78-a3e2-4cac-868d-c4ae8b39b2fc
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMTSetContextSchedulingPriority, D3DKMTSetContextSchedulingPriority function [Display Devices], OpenGL_Functions_f9314ed6-8aad-4c55-b42a-f1223dada5bc.xml, d3dkmthk/D3DKMTSetContextSchedulingPriority, display.d3dkmtsetcontextschedulingpriority
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Gdi32.dll
-	API-MS-Win-dx-d3dkmt-l1-1-0.dll
-	API-MS-Win-dx-d3dkmt-l1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
-	D3DKMTSetContextSchedulingPriority
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---


# D3DKMTSetContextSchedulingPriority function
The <b>D3DKMTSetContextSchedulingPriority</b> function sets the scheduling priority for a device context.

## Syntax

````
NTSTATUS APIENTRY D3DKMTSetContextSchedulingPriority(
  _In_ const D3DKMT_SETCONTEXTSCHEDULINGPRIORITY *pData
);
````

## Parameters

`D3DKMT_SETCONTEXTSCHEDULINGPRIORITY`

TBD


## Return Value

<b>D3DKMTSetContextSchedulingPriority</b> returns one of the following values:

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
The scheduling priority was successfully set.

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
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Universal |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |
| **Library** | Gdi32.lib |
| **DLL** | Gdi32.dll |

## See Also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_setcontextschedulingpriority.md">D3DKMT_SETCONTEXTSCHEDULINGPRIORITY</a>
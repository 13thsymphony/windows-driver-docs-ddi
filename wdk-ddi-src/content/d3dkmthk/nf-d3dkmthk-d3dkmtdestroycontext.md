---
UID: NF:d3dkmthk.D3DKMTDestroyContext
title: D3DKMTDestroyContext function
author: windows-driver-content
description: The D3DKMTDestroyContext function releases a kernel-mode device context.
old-location: display\d3dkmtdestroycontext.htm
old-project: display
ms.assetid: 33c10139-7a9a-41b1-a3c4-e3692be9a34a
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMTDestroyContext, D3DKMTDestroyContext function [Display Devices], OpenGL_Functions_f7a43a18-cb8c-4b76-8123-d5eeda18d6cb.xml, d3dkmthk/D3DKMTDestroyContext, display.d3dkmtdestroycontext
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
-	D3DKMTDestroyContext
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---


# D3DKMTDestroyContext function
The <b>D3DKMTDestroyContext</b> function releases a kernel-mode device context.

## Syntax

```
NTSTATUS D3DKMTDestroyContext(
  CONST *D3DKMT_DESTROYCONTEXT
);
```

## Parameters

`D3DKMT_DESTROYCONTEXT`

TBD


## Return Value

<b>D3DKMTDestroyContext</b> returns one of the following values:

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
The device context was successfully released.

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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547869">D3DKMT_DESTROYCONTEXT</a>
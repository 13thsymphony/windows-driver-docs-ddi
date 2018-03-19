---
UID: NF:d3dkmthk.D3DKMTDestroyDCFromMemory
title: D3DKMTDestroyDCFromMemory function
author: windows-driver-content
description: The D3DKMTDestroyDCFromMemory function releases the display context.
old-location: display\d3dkmtdestroydcfrommemory.htm
old-project: display
ms.assetid: 1c34db7b-6153-40ec-9a9f-72b9c04c9f12
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMTDestroyDCFromMemory, D3DKMTDestroyDCFromMemory function [Display Devices], OpenGL_Functions_2c70707b-7052-4f5f-8715-e2e61a7ab267.xml, d3dkmthk/D3DKMTDestroyDCFromMemory, display.d3dkmtdestroydcfrommemory
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
-	D3DKMTDestroyDCFromMemory
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---


# D3DKMTDestroyDCFromMemory function
The <b>D3DKMTDestroyDCFromMemory</b> function releases the display context.

## Syntax

````
NTSTATUS D3DKMTDestroyDCFromMemory(
  _In_ const D3DKMT_DESTROYDCFROMMEMORY *pData
);
````

## Parameters

`D3DKMT_DESTROYDCFROMMEMORY`

TBD


## Return Value

<b>D3DKMTDestroyDCFromMemory</b> returns one of the following values:

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
 

This function might also return other <b>NTSTATUS</b> values.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Universal |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |
| **Library** | Gdi32.lib |
| **DLL** | Gdi32.dll |

## See Also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_destroydcfrommemory.md">D3DKMT_DESTROYDCFROMMEMORY</a>
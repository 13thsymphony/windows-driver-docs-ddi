---
UID: NF:d3dkmthk.D3DKMTDestroyAllocation2
title: D3DKMTDestroyAllocation2 function
author: windows-driver-content
description: The D3DKMTDestroyAllocation2 function releases a resource, a list of allocations, or both.
old-location: display\d3dkmtdestroyallocation2.htm
old-project: display
ms.assetid: C66CD2FB-AD45-4666-ACD4-6555ED681935
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMTDestroyAllocation2, D3DKMTDestroyAllocation2 function [Display Devices], d3dkmthk/D3DKMTDestroyAllocation2, display.d3dkmtdestroyallocation2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: GDI32.lib
req.dll: GDI32.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	GDI32.dll
-	API-MS-Win-DX-D3DKMT-L1-1-1.dll
-	GDI32.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
-	D3DKMTDestroyAllocation2
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---


# D3DKMTDestroyAllocation2 function
The <b>D3DKMTDestroyAllocation2</b> function releases a resource, a list of allocations, or both.

## Syntax

```
NTSTATUS D3DKMTDestroyAllocation2(
  CONST *D3DKMT_DESTROYALLOCATION2
);
```

## Parameters

`D3DKMT_DESTROYALLOCATION2`

TBD


## Return Value

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546891">D3DKMTDestroyAllocation</a> returns one of the following values:

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
Allocations were successfully released.

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
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Universal |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |
| **Library** | GDI32.lib |
| **DLL** | GDI32.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn906793">D3DKMT_DESTROYALLOCATION2</a>
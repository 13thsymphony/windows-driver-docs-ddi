---
UID: NF:d3dkmthk.D3DKMTLock2
title: D3DKMTLock2 function
author: windows-driver-content
description: The D3DKMTLock2 function locks an entire allocation or specific pages within an allocation.
old-location: display\d3dkmtlock2.htm
old-project: display
ms.assetid: 033FF321-2617-4AAF-8445-10800411F0B5
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMTLock2, D3DKMTLock2 function [Display Devices], d3dkmthk/D3DKMTLock2, display.d3dkmtlock2
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
-	API-MS-Win-DX-D3DKMT-L1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
-	D3DKMTLock2
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---


# D3DKMTLock2 function
The <b>D3DKMTLock2</b> function locks an entire allocation or specific pages within an allocation.

## Syntax

```
NTSTATUS D3DKMTLock2(

);
```

## Parameters

This function has no parameters.

## Return Value

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
The allocation was successfully locked.

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
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_ALLOCATION_BUSY</b></dt>
</dl>
</td>
<td width="60%">
The allocation was currently in use and could not be locked.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_TOO_MANY_REFERENCES</b></dt>
</dl>
</td>
<td width="60%">
Too many references were pending on the allocation.

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
| **Library** | Gdi32.lib |
| **DLL** | Gdi32.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn914439">D3DKMT_LOCK2</a>
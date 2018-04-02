---
UID: NF:d3dkmthk.D3DKMTQueryAdapterInfo
title: D3DKMTQueryAdapterInfo function
author: windows-driver-content
description: The D3DKMTQueryAdapterInfo function retrieves graphics adapter information.
old-location: display\d3dkmtqueryadapterinfo.htm
old-project: display
ms.assetid: fa67207d-cf83-42a5-969b-29379f99883f
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMTQueryAdapterInfo, D3DKMTQueryAdapterInfo function [Display Devices], OpenGL_Functions_124c9878-58d2-414b-8b3c-392748ca5361.xml, d3dkmthk/D3DKMTQueryAdapterInfo, display.d3dkmtqueryadapterinfo
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
-	D3DKMTQueryAdapterInfo
product:
- Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---


# D3DKMTQueryAdapterInfo function
The <b>D3DKMTQueryAdapterInfo</b> function retrieves graphics adapter information.

## Syntax

```
NTSTATUS D3DKMTQueryAdapterInfo(
  CONST *D3DKMT_QUERYADAPTERINFO
);
```

## Parameters

`D3DKMT_QUERYADAPTERINFO`

TBD


## Return Value

<b>D3DKMTQueryAdapterInfo</b> returns one of the following values:

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
Graphics adapter information was successfully retrieved.

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
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547100">D3DKMTQueryAdapterInfo</a> could not complete because of insufficient memory.

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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547195">D3DKMTSetQueuedLimit</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548203">D3DKMT_QUERYADAPTERINFO</a>
---
UID: NF:d3dkmthk.D3DKMTCreateOverlay
title: D3DKMTCreateOverlay function
author: windows-driver-content
description: The D3DKMTCreateOverlay function creates a kernel-mode overlay object.
old-location: display\d3dkmtcreateoverlay.htm
old-project: display
ms.assetid: f77c20a1-c05c-456b-874b-e07d6edf5982
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMTCreateOverlay, D3DKMTCreateOverlay function [Display Devices], OpenGL_Functions_3848b4de-9ed0-4e4f-87aa-677bdbbaa7e0.xml, d3dkmthk/D3DKMTCreateOverlay, display.d3dkmtcreateoverlay
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
-	D3DKMTCreateOverlay
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---


# D3DKMTCreateOverlay function
The <b>D3DKMTCreateOverlay</b> function creates a kernel-mode overlay object.

## Syntax

````
NTSTATUS D3DKMTCreateOverlay(
  _Inout_ D3DKMT_CREATEOVERLAY *pData
);
````

## Parameters

This function has no parameters.

## Return Value

<b>D3DKMTCreateOverlay</b> returns one of the following values:

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
The kernel-mode overlay object was successfully created.

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
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreateoverlay.md">D3DKMTCreateOverlay</a> could not complete because of insufficient memory.

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

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_createoverlay.md">D3DKMT_CREATEOVERLAY</a>
---
UID: NF:d3dkmthk.D3DKMTAcquireKeyedMutex
title: D3DKMTAcquireKeyedMutex function
author: windows-driver-content
description: The D3DKMTAcquireKeyedMutex function acquires a keyed mutex object.
old-location: display\d3dkmtacquirekeyedmutex.htm
old-project: display
ms.assetid: 0d9627c3-ed1d-49d4-bdca-bc0e49efc234
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMTAcquireKeyedMutex, D3DKMTAcquireKeyedMutex callback function [Display Devices], OpenGL_Functions_547da245-f41b-4e73-bf9c-7a72f6104def.xml, PFND3DKMT_ACQUIREKEYEDMUTEX, d3dkmthk/D3DKMTAcquireKeyedMutex, display.d3dkmtacquirekeyedmutex
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: D3DKMTAcquireKeyedMutex is supported beginning with the Windows 7 operating system.
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
-	D3DKMTAcquireKeyedMutex
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---


# D3DKMTAcquireKeyedMutex function
The <b>D3DKMTAcquireKeyedMutex</b> function acquires a keyed mutex object.

## Syntax

````
NTSTATUS APIENTRY D3DKMTAcquireKeyedMutex(
  _Inout_ D3DKMT_ACQUIREKEYEDMUTEX *pData
);
````

## Parameters

This function has no parameters.

## Return Value

<b>D3DKMTAcquireKeyedMutex</b> returns one of the following values:

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
The keyed mutex object was successfully acquired. 

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

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtacquirekeyedmutex.md">D3DKMTAcquireKeyedMutex</a> could not complete because of insufficient memory.

</td>
</tr>
</table>
 

This function might also return other <b>NTSTATUS</b> values.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | D3DKMTAcquireKeyedMutex is supported beginning with the Windows 7 operating system.  |
| **Target Platform** | Universal |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_acquirekeyedmutex.md">D3DKMT_ACQUIREKEYEDMUTEX</a>
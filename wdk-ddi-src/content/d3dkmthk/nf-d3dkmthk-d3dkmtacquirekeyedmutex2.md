---
UID: NF:d3dkmthk.D3DKMTAcquireKeyedMutex2
title: D3DKMTAcquireKeyedMutex2 function
author: windows-driver-content
description: Acquires a keyed mutex object that includes private data.
old-location: display\d3dkmtacquirekeyedmutex2.htm
old-project: display
ms.assetid: 94ebfeb6-2035-4dd6-bbc9-ba82939b51ec
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMTAcquireKeyedMutex2, D3DKMTAcquireKeyedMutex2 callback function [Display Devices], PFND3DKMT_ACQUIREKEYEDMUTEX2, d3dkmthk/D3DKMTAcquireKeyedMutex2, display.d3dkmtacquirekeyedmutex2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	d3dkmthk.h
api_name:
-	D3DKMTAcquireKeyedMutex2
product:
- Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---


# D3DKMTAcquireKeyedMutex2 function
Acquires a keyed mutex object that includes private data.

## Syntax

```
NTSTATUS D3DKMTAcquireKeyedMutex2(

);
```

## Parameters

This function has no parameters.

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

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439340">D3DKMTAcquireKeyedMutex2</a> could not complete because of insufficient memory.

</td>
</tr>
</table>
 

This function might also return other <b>NTSTATUS</b> values.

## Remarks

<b>D3DKMTAcquireKeyedMutex2</b> behaves like the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546732">D3DKMTAcquireKeyedMutex</a> function but lets the caller specify private data to associate with the keyed mutex.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Universal |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546732">D3DKMTAcquireKeyedMutex</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439466">D3DKMT_ACQUIREKEYEDMUTEX2</a>
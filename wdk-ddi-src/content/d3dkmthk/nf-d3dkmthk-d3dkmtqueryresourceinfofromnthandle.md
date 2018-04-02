---
UID: NF:d3dkmthk.D3DKMTQueryResourceInfoFromNtHandle
title: D3DKMTQueryResourceInfoFromNtHandle function
author: windows-driver-content
description: Maps a global NT handle to resource information that is needed for a call to the D3DKMTQueryResourceInfo function.
old-location: display\d3dkmtqueryresourceinfofromnthandle.htm
old-project: display
ms.assetid: 7a433aaf-3215-4d11-8989-2d7bdc7f7499
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMTQueryResourceInfoFromNtHandle, D3DKMTQueryResourceInfoFromNtHandle callback function [Display Devices], PFND3DKMT_QUERYRESOURCEINFOFROMNTHANDLE, d3dkmthk/D3DKMTQueryResourceInfoFromNtHandle, display.d3dkmtqueryresourceinfofromnthandle
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
-	D3dkmthk.h
api_name:
-	D3DKMTQueryResourceInfoFromNtHandle
product:
- Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---


# D3DKMTQueryResourceInfoFromNtHandle function
Maps a global NT handle  to resource information that is needed for a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547124">D3DKMTQueryResourceInfo</a> function.

## Syntax

```
NTSTATUS D3DKMTQueryResourceInfoFromNtHandle(

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
The mapping was performed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER </b></dt>
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
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Universal |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547124">D3DKMTQueryResourceInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406560">D3DKMT_QUERYRESOURCEINFOFROMNTHANDLE</a>
---
UID: NF:d3dkmthk.D3DKMTOpenSyncObjectFromNtHandle
title: D3DKMTOpenSyncObjectFromNtHandle function
author: windows-driver-content
description: Maps an NT process handle to a graphics processing unit (GPU) synchronization object.
old-location: display\d3dkmtopensyncobjectfromnthandle.htm
old-project: display
ms.assetid: 202695a2-cfe3-423f-b4da-a9ad312c5168
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMTOpenSyncObjectFromNtHandle, D3DKMTOpenSyncObjectFromNtHandle function [Display Devices], d3dkmthk/D3DKMTOpenSyncObjectFromNtHandle, display.d3dkmtopensyncobjectfromnthandle
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
-	API-MS-Win-dx-d3dkmt-l1-1-0.dll
-	API-MS-Win-dx-d3dkmt-l1-1-1.dll
-	API-MS-Win-DX-D3DKMT-L1-1-2.dll
api_name:
-	D3DKMTOpenSyncObjectFromNtHandle
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---


# D3DKMTOpenSyncObjectFromNtHandle function
Maps an NT process handle to a graphics processing unit (GPU) synchronization object.

## Syntax

````
EXTERN_C _Check_return_ NTSTATUS APIENTRY D3DKMTOpenSyncObjectFromNtHandle(
  _Inout_ D3DKMT_OPENSYNCOBJECTFROMNTHANDLE *pObject
);
````

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
| **Library** | GDI32.lib |
| **DLL** | GDI32.dll |

## See Also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_opensyncobjectfromnthandle.md">D3DKMT_OPENSYNCOBJECTFROMNTHANDLE</a>